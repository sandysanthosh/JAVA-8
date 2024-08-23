Here is the Java 8 code for each of the operations you've described:

```java
import java.util.*;
import java.util.stream.*;

public class StreamExamples {

    public static void main(String[] args) {

        // filter: Fetch all numbers from a list that are greater than 5.
        List<Integer> numbers = Arrays.asList(1, 2, 6, 7, 3, 4, 10);
        List<Integer> filteredNumbers = numbers.stream()
                                                .filter(n -> n > 5)
                                                .collect(Collectors.toList());
        System.out.println("Filtered Numbers (greater than 5): " + filteredNumbers);

        // map: Transform a list of strings into a list of their uppercase versions.
        List<String> strings = Arrays.asList("java", "stream", "api");
        List<String> uppercasedStrings = strings.stream()
                                                .map(String::toUpperCase)
                                                .collect(Collectors.toList());
        System.out.println("Uppercased Strings: " + uppercasedStrings);

        // flatMap: Flatten a list of lists of strings into a single list of strings.
        List<List<String>> listOfLists = Arrays.asList(
            Arrays.asList("a", "b"),
            Arrays.asList("c", "d"),
            Arrays.asList("e", "f")
        );
        List<String> flattenedList = listOfLists.stream()
                                                .flatMap(List::stream)
                                                .collect(Collectors.toList());
        System.out.println("Flattened List: " + flattenedList);

        // distinct: Remove duplicates from a list of integers.
        List<Integer> numbersWithDuplicates = Arrays.asList(1, 2, 3, 2, 4, 1, 5);
        List<Integer> distinctNumbers = numbersWithDuplicates.stream()
                                                             .distinct()
                                                             .collect(Collectors.toList());
        System.out.println("Distinct Numbers: " + distinctNumbers);

        // sorted: Sort a list of names in reverse alphabetical order.
        List<String> names = Arrays.asList("John", "Alice", "Bob");
        List<String> sortedNames = names.stream()
                                        .sorted(Comparator.reverseOrder())
                                        .collect(Collectors.toList());
        System.out.println("Names in Reverse Alphabetical Order: " + sortedNames);

        // peek: Print each element in a list while converting them to uppercase.
        List<String> peekedStrings = strings.stream()
                                            .peek(s -> System.out.println("Original: " + s))
                                            .map(String::toUpperCase)
                                            .peek(s -> System.out.println("Uppercased: " + s))
                                            .collect(Collectors.toList());

        // limit: Fetch the first 3 elements from a list of integers.
        List<Integer> limitedNumbers = numbers.stream()
                                              .limit(3)
                                              .collect(Collectors.toList());
        System.out.println("First 3 Numbers: " + limitedNumbers);

        // skip: Skip the first 4 elements and fetch the remaining elements from a list of integers.
        List<Integer> skippedNumbers = numbers.stream()
                                              .skip(4)
                                              .collect(Collectors.toList());
        System.out.println("Skipped First 4 Numbers: " + skippedNumbers);

        // forEach: Print each element of a list of strings with a prefix "Item: ".
        strings.forEach(s -> System.out.println("Item: " + s));

        // collect: Collect a list of integers into a Set.
        Set<Integer> numberSet = numbers.stream()
                                        .collect(Collectors.toSet());
        System.out.println("Collected Set: " + numberSet);

        // reduce: Compute the product of all numbers in a list.
        Optional<Integer> product = numbers.stream()
                                           .reduce((a, b) -> a * b);
        product.ifPresent(p -> System.out.println("Product of All Numbers: " + p));

        // allMatch: Check if all numbers in a list are positive.
        boolean allPositive = numbers.stream()
                                     .allMatch(n -> n > 0);
        System.out.println("All numbers are positive: " + allPositive);

        // anyMatch: Check if any number in the list is even.
        boolean anyEven = numbers.stream()
                                 .anyMatch(n -> n % 2 == 0);
        System.out.println("Any number is even: " + anyEven);

        // noneMatch: Check if no elements in a list are negative.
        boolean noneNegative = numbers.stream()
                                      .noneMatch(n -> n < 0);
        System.out.println("No numbers are negative: " + noneNegative);

        // findFirst: Find the first number greater than 5 in the list.
        Optional<Integer> firstGreaterThanFive = numbers.stream()
                                                        .filter(n -> n > 5)
                                                        .findFirst();
        firstGreaterThanFive.ifPresent(n -> System.out.println("First number greater than 5: " + n));
    }
}
```

### Explanation of Each Code Block:
1. **filter:** Selects numbers greater than 5 from the list.
2. **map:** Converts each string in the list to uppercase.
3. **flatMap:** Flattens a list of lists into a single list.
4. **distinct:** Removes duplicates from a list of integers.
5. **sorted:** Sorts a list of names in reverse alphabetical order.
6. **peek:** Prints elements in their original form and after converting them to uppercase.
7. **limit:** Retrieves the first 3 elements from the list.
8. **skip:** Skips the first 4 elements and collects the remaining elements.
9. **forEach:** Prints each string in the list with a prefix.
10. **collect:** Collects the list of integers into a `Set`.
11. **reduce:** Computes the product of all numbers in the list.
12. **allMatch:** Checks if all numbers in the list are positive.
13. **anyMatch:** Checks if any number in the list is even.
14. **noneMatch:** Checks if there are no negative numbers in the list.
15. **findFirst:** Finds the first number greater than 5 in the list.

This should give you a comprehensive guide to using these Java 8 stream operations!
