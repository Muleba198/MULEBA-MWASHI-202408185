MULEBA MWASHI 202408185

INFIX TO POST FIX.
FUNCTION infixToPostfix(expression):
    Initialize an empty Stack for operators
    Initialize an empty String for result
    
    FOR each character 'c' in expression:
        IF 'c' is an operand (letter or digit):
            Append 'c' to result
        
        ELSE IF 'c' is '(':
            Push 'c' onto Stack
            
        ELSE IF 'c' is ')':
            WHILE Stack is not empty AND Stack top is not '(':
                Append Stack.pop() to result
            Pop '(' from Stack (discard it)
            
        ELSE (if 'c' is an operator):
            WHILE Stack is not empty AND precedence(c) <= precedence(Stack.top):
                Append Stack.pop() to result
            Push 'c' onto Stack
            
    WHILE Stack is not empty:
        Append Stack.pop() to result
        
    RETURN result



INFIX TO POSTFIX.


    FUNCTION infixToPostfix(expression):
    Initialize an empty Stack for operators
    Initialize an empty String for result
    
    FOR each character 'c' in expression:
        IF 'c' is an operand (letter or digit):
            Append 'c' to result
        
        ELSE IF 'c' is '(':
            Push 'c' onto Stack
            
        ELSE IF 'c' is ')':
            WHILE Stack is not empty AND Stack top is not '(':
                Append Stack.pop() to result
            Pop '(' from Stack (discard it)
            
        ELSE (if 'c' is an operator):
            WHILE Stack is not empty AND precedence(c) <= precedence(Stack.top):
                Append Stack.pop() to result
            Push 'c' onto Stack
            
    WHILE Stack is not empty:
        Append Stack.pop() to result


        **EXPLANATION OF THE TWO PSEUDO CODES.**
        Logic and Implementation
This project uses the Shunting-Yard Algorithm logic to transform standard math notation (Infix) into formats that are easier for computers to evaluate (Postfix and Prefix).

1.** Infix to Postfix (Reverse Polish Notation)**
In Postfix, operators follow their operands (e.g., A + B becomes AB+).
The Process: We scan the expression from left to right.
Operands: Are added immediately to the output string.
Operators: Are pushed onto a Stack. However, if an operator with higher or equal "power" (precedence) is already on the stack, it must be moved to the output first to ensure the math stays correct.
Parentheses: Act as a local boundary; when a closing bracket ) is met, the stack is cleared out until the matching ( is found.

2. **Infix to Prefix (Polish Notation)**
In Prefix, operators precede their operands (e.g., A + B becomes +AB).
The Process: Instead of creating a whole new algorithm, we use a Reversal Strategy.

Step 1: Reverse the Infix string and swap the parentheses (so they still face the right way).
Step 2: Run the standard Postfix algorithm on this reversed string.
Step 3: Reverse the final result once more. This naturally places the operators at the beginning of the expression.
    RETURN result
