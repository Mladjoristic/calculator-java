import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

import java.util.List;
import java.util.ArrayList;

public class CalculatorTest {

    @Test
    public void testCalculate() {
        // Test sa jednostavnim sabiranjem
        List<Float> numbers = new ArrayList<>();
        numbers.add(5f);
        numbers.add(3f);
        
        List<String> operations = new ArrayList<>();
        operations.add("+");
        
        Calculator.Calculate(numbers, operations);
        
        assertEquals(8f, Calculator.finalResult);
        
        // Test sa deljenjem
        numbers.clear();
        numbers.add(6f);
        numbers.add(2f);
        
        operations.clear();
        operations.add("/");
        
        Calculator.Calculate(numbers, operations);
        
        assertEquals(3f, Calculator.finalResult);
        
        // Test sa prioritetom množenja
        numbers.clear();
        numbers.add(5f);
        numbers.add(2f);
        numbers.add(3f);
        
        operations.clear();
        operations.add("*");
        operations.add("+");
        
        Calculator.Calculate(numbers, operations);
        
        assertEquals(11f, Calculator.finalResult); // (5 * 2) + 3 = 11
    }
}

