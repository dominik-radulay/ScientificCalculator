import java.util.Scanner;
import java.lang.Math;

public class ScientificCalculator {

    public static void main(String[] args) {
        // Create a scanner object to read user input
        Scanner scanner = new Scanner(System.in);

        // Display a welcome message and prompt the user for input
        System.out.println("Welcome to the Scientific Calculator!");
        System.out.print("Enter a mathematical expression: ");

        // Read the user input as a string
        String expression = scanner.nextLine();

        // Evaluate the expression using the eval() method
        double result = eval(expression);

        // Display the result to the user
        System.out.println("Result: " + result);

        // Close the scanner object
        scanner.close();
    }

    // A recursive method that evaluates a mathematical expression
    private static double eval(String expression) {
        // Remove any whitespace from the expression
        expression = expression.replaceAll("\\s+", "");

        // Check for a single value or expression in parentheses
        if (expression.startsWith("(") && expression.endsWith(")")) {
            // Recursively evaluate the expression inside the parentheses
            return eval(expression.substring(1, expression.length() - 1));
        }

        // Check for addition or subtraction operators
        int operatorIndex = -1;
        char operator = ' ';
        for (int i = 0; i < expression.length(); i++) {
            char c = expression.charAt(i);
            if (c == '+' || c == '-') {
                operatorIndex = i;
                operator = c;
                break;
            }
        }
        if (operatorIndex != -1) {
            // Split the expression into two parts and evaluate each part recursively
            String left = expression.substring(0, operatorIndex);
            String right = expression.substring(operatorIndex + 1);
            double leftValue = eval(left);
            double rightValue = eval(right);
            if (operator == '+') {
                return leftValue + rightValue;
            } else {
                return leftValue - rightValue;
            }
        }

        // Check for multiplication or division operators
        operatorIndex = -1;
        operator = ' ';
        for (int i = 0; i < expression.length(); i++) {
            char c = expression.charAt(i);
            if (c == '*' || c == '/') {
                operatorIndex = i;
                operator = c;
                break;
            }
        }
        if (operatorIndex != -1) {
            // Split the expression into two parts and evaluate each part recursively
            String left = expression.substring(0, operatorIndex);
            String right = expression.substring(operatorIndex + 1);
            double leftValue = eval(left);
            double rightValue = eval(right);
            if (operator == '*') {
                return leftValue * rightValue;
            } else {
                return leftValue / rightValue;
            }
        }

        // Check for exponentiation operator
        operatorIndex = expression.indexOf('^');
        if (operatorIndex != -1) {
            // Split the expression into two parts and evaluate each part recursively
            String left = expression.substring(0, operatorIndex);
            String right = expression.substring(operatorIndex + 1);
            double leftValue = eval(left);
            double rightValue = eval(right);
            return Math.pow(leftValue, rightValue);
        }

        // Check for square root function
        if (expression.startsWith("sqrt(") && expression.endsWith(")")) {
            // Evaluate the expression inside the square root function recursively
            double value = eval(expression.substring(5, expression.length() - 1));
            return Math.sqrt(value);
        }

        // Check for trigonometric functions
        if (expression
                .startsWith("sin(") && expression.endsWith(")")) {
            // Evaluate the expression inside the sin function recursively
            double value = eval(expression.substring(4, expression.length() - 1));
            return Math.sin(value);
        } else if (expression.startsWith("cos(") && expression.endsWith(")")) {
            // Evaluate the expression inside the cos function recursively
            double value = eval(expression.substring(4, expression.length() - 1));
            return Math.cos(value);
        } else if (expression.startsWith("tan(") && expression.endsWith(")")) {
            // Evaluate the expression inside the tan function recursively
            double value = eval(expression.substring(4, expression.length() - 1));
            return Math.tan(value);
        }

        // Check for logarithmic functions
        if (expression.startsWith("log(") && expression.endsWith(")")) {
            // Split the expression into two parts and evaluate each part recursively
            String baseString = expression.substring(4, expression.indexOf(","));
            String valueString = expression.substring(expression.indexOf(",") + 1, expression.length() - 1);
            double base = eval(baseString);
            double value = eval(valueString);
            return Math.log(value) / Math.log(base);
        } else if (expression.startsWith("ln(") && expression.endsWith(")")) {
            // Evaluate the expression inside the ln function recursively
            double value = eval(expression.substring(3, expression.length() - 1));
            return Math.log(value);
        }

        // If none of the above conditions are met, the expression must be a single value
        return Double.parseDouble(expression);
    }
}
// This calculator can evaluate basic arithmetic expressions, as well as expressions involving parentheses, addition, subtraction, multiplication, division, exponentiation, square roots, and trigonometric and logarithmic functions. Note that this is a simplified example and does not handle all possible mathematical expressions.
