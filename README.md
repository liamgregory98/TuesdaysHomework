# Tuesdays Homework
## Word Counter
```java
public class WordCounter {
    public static void main(String[] args) {

        System.out.println("Please enter a sentence");
        Scanner userInput = new Scanner(System.in);
        String sentence = userInput.nextLine();
        System.out.println("Please enter a letter");
        char letter = userInput.next().charAt(0);
        countWords(sentence, letter);
    }

    private static void countWords(String sentence, char letter) {
        int counter = 0;
        letter = Character.toLowerCase(letter);
        String words[] = sentence.toLowerCase().split(" ");
        System.out.println(words);
        for (int i = 0; i < words.length; i++) {
            String s = words[i];
            if (s.charAt(0) == letter) {
                counter++;
            }
        }
        System.out.println(counter);
    }
}
```
## Word Counter Tests

```java
class WordCounterTest {
    @Test
    @DisplayName("Given a sentence and a letter, WordCounter returns how many words in the sentence begin with the letter")
    public void givenASentenceAndLetter_WordCounter_ReturnsNumberOfWordsBeginningWithLetter(){
        String sentence = "Hello my name is Harry Hill";
        char letter = 'h';
        int expectedCount = 3;
        int result = WordCounter.countWords(sentence,letter);
        assertEquals(expectedCount, result);
    }//Test Passed

    @Test
    @DisplayName("Given a sentence and a letter, WordCounter returns how many words in the sentence begin with the letter")
    public void givenASentenceAndLetter_WordCounter_ReturnsNumberOfWordsBeginningWithLetterIndependentOfCase(){
        String sentence = "mercury venus earth mars jupiter saturn neptune uranus";
        char letter = 'U';
        int expectedCount = 1;
        int result = WordCounter.countWords(sentence,letter);
        assertEquals(expectedCount, result);
    }//Test Passed

    @Test
    @DisplayName("Given a sentence and a letter, WordCounter returns how many words in the sentence begin with the letter")
    public void givenASentenceAndLetter_WordCounter_ReturnsNofWordsIfLetterDoesNotMatch(){
        String sentence = "mercury venus earth mars jupiter saturn neptune uranus";
        char letter = 'p';
        int expectedCount = 0;
        int result = WordCounter.countWords(sentence,letter);
        assertEquals(expectedCount, result);
    }//Test Passed
```

## Summer Code

```java
public class Summer {
    public static void main(String[] args) {
        int[] myInts = {1, 2, 3, 4, 5};
        Summer summer = new Summer();
        System.out.println(summer.sumArray(myInts));

    }
    public static int sumArray(int[] myInts){
        int sumArray = 0;
        for(int i = 0; i <= myInts.length -1; i++) {
            sumArray += myInts[i];
        }
        return sumArray;
    }
```
## Summer Tests
```java
class SummerTest {
    @Test
    @DisplayName("Given an Int Array, Summer will return the sum of the values inside the array")
    public void givenAnIntArray_Summer_ReturnsTheSumOfTheValuesInsideTheArray(){
        int[] myInts = {3, 8, 9, 12, 26};
        int expectedResult = 58;
        int result = Summer.sumArray(myInts);
        assertEquals(expectedResult, result);
    } //Test Passed

    @Test
    @DisplayName("Given an Int Array, Summer will return the sum of the values inside the array")
    public void givenAnIntArray_Summer_ReturnsTheSumOfTheValuesInsideTheArrayEvenNegativeNumbers(){
        int[] myInts = {3, -8, 9, -12, 26, 100};
        int expectedResult = 118;
        int result = Summer.sumArray(myInts);
        assertEquals(expectedResult, result);
    } //Test Passed
```

## Planets Enum
```java
public enum Planets {
    MERCURY(70, 3.3E+23),
    VENUS(109, 4.9E+23),
    EARTH(148, 6.0E+24),
    MARS(228, 6.4E+23),
    JUPITER(778, 1.9E+27),
    SATURN(1427, 5.7E+26),
    URANUS(2871, 8.7E+25),
    NEPTUNE(4497, 10.2E+25);

    private final int distanceFromSunMKm;
    private final double massKg;

    private Planets(int distanceFromSunMK, double massKg){
        this.distanceFromSunMKm = distanceFromSunMK;
        this.massKg = massKg;
    }
    public int getDistanceFromSunMKm(){
        return distanceFromSunMKm;
    }

    public double getMassKg() {return massKg;}
}
```
