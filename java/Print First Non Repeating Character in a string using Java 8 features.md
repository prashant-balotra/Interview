```
import java.util.*;
import java.util.function.Function;
import java.util.stream.Collectors;

public class FirstNonRepeatingCharacter {
  public static void main(String args[]) {
    ("swiss").chars()
                .mapToObj(c -> (char) c)
                .collect(
                        Collectors.groupingBy(Function.identity(),
                                LinkedHashMap::new,
                                Collectors.counting()
                        )
                ).entrySet().stream()
                .filter(e -> e.getValue() == 1)
                .findFirst()
                .map(Map.Entry::getKey)
                .ifPresent(System.out::print);
  }
}
```
