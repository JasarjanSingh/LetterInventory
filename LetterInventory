// Jasarjan Singh
// 4/14/2022
// CSE 143
// TA: Himani Nijhawan
// Assesment #1 Letter Inventory
// This program is used to store the letter counts of the alphabet
// for a given String input. 

public class LetterInventory {
    private int size;
    private int[] elementData;
    public static final int ALPHABET_CAPACITY = 26;

    // post: Constructs an empty inventory 
    public LetterInventory() {
        elementData = new int[ALPHABET_CAPACITY];
        size = 0;
    }

    // post: Constructs an inventory a count of the alphabetic 
    //       letters in the given string
    public LetterInventory(String data) {
        elementData = new int[ALPHABET_CAPACITY];
        data = data.toLowerCase();
        for(int i = 0; i < data.length(); i++) {
            if(Character.isLetter(data.charAt(i))) {
                elementData[data.charAt(i) - 'a']++;
                size++;
            }
        }
    }

    // post: returns the sum of all of the counts in this inventory
    public int size() {
        return size;
    }

    // post: returns true if this inventory is empty (all counts are 0)
    //       returns false otherwise
    public boolean isEmpty() {
        return size == 0;
    }

    // post: Returns an alphabetically organized String representation 
    //       of the inventory with all the letters in lowercase
    public String toString() {
        String result = "[";
        for(int i = 0; i < ALPHABET_CAPACITY; i++) {
            for(int j = 0; j < elementData[i]; j++) {
                result = result + (char)(i + 'a');
            }
        }
        return result + "]";
    }

    // pre: LetterInventory other parameter
    // post: returns a new LetterInventory object that represents the sum 
    //       of this LetterInventory and the other given LetterInventory
    public LetterInventory add(LetterInventory other) {
        LetterInventory sum = new LetterInventory("");
        for (int i = 0; i < ALPHABET_CAPACITY; i++) {
            char letter = (char)(i + 'a');
            sum.set(letter, (elementData[i] + other.get(letter)));
        }
        return sum;
    }

    // pre: LetterInventory other parameter
    // post: returns a new LetterInventory object that represents 
    //       the difference of this LetterInventory and the other 
    //       given LetterInventory
    public LetterInventory subtract(LetterInventory other) {
        LetterInventory difference = new LetterInventory("");
        for (int i = 0; i < ALPHABET_CAPACITY; i++) {
            char letter = (char)(i + 'a');
            int count = elementData[i] - other.get(letter);
            if (count < 0) {
                return null;
            } else {
                difference.set(letter, count);
            }
        }
        return difference;
    }

    // pre: throws IllegalArgumentException if a non-alphabetic
    //      character is passed or if value is negative
    // post: Sets the count for the given letter to the given value
    public void set(char letter, int value) {
        if(!Character.isLetter(letter) || value < 0){
            throw new IllegalArgumentException();
        }
        letter = Character.toLowerCase(letter);
        size += (value - elementData[letter - 'a']);
        elementData[letter - 'a'] = value;
    }

    // pre: throws IllegalArgumentException if a non-alphabetic
    //      character is passed
    // post: returns a count of how many of the given 
    //       letter are in this inventory
    public int get(char letter) {
        if(!Character.isLetter(letter)){
            throw new IllegalArgumentException();
        }
        letter = Character.toLowerCase(letter);
        return elementData[letter - 'a'];
    }
}
   
