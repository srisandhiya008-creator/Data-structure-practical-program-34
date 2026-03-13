# Prefix Expression Evaluation using Stack

def prefix_eval(expr):
    stack = []

    # traverse expression from right to left
    for i in reversed(expr):
        if i.isdigit():          # operand
            stack.append(int(i))
        else:                    # operator
            a = stack.pop()
            b = stack.pop()

            if i == '+':
                stack.append(a + b)
            elif i == '-':
                stack.append(a - b)
            elif i == '*':
                stack.append(a * b)
            elif i == '/':
                stack.append(a / b)

    return stack.pop()


# real-time example
exp = "-+7*45+20"

print("Prefix Expression:", exp)
print("Result:", prefix_eval(exp))# Data-structure-practical-program-34
