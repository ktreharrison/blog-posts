# Sourcery: A Free Tool for Better Python Code!

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1676019509905/4432c295-210c-47d8-9bf0-f7059d315bd4.png)

Image to accompany the article. An image of an expression grand wizard and witch making computer code.

Python is a popular programming language for its simplicity and versatility. However, even experienced Python developers can make mistakes or write code that is difficult to maintain. Enter [**Sourcery**](https://sourcery.ai/invite/kqMdSInZ), an open source tool that helps you write better Python code by automating common code patterns and catching errors before they become a problem. There’s also a pro version that packed with full project scan, **d**uplicate code detection and advanced refactorings.

[**Sourcery**](https://sourcery.ai/invite/kqMdSInZ) is a static code analysis tool for Python. It uses advanced algorithms to detect and correct common issues in your code, such as typos, formatting errors, and incorrect variable names. [**Sourcery**](https://sourcery.ai/invite/kqMdSInZ) also offers automated refactoring tools that help you optimize your code for readability and performance. By using [Sourcery](https://sourcery.ai/invite/kqMdSInZ), developers can quickly identify potential issues with their code before they become an issue and ensure their projects are up-to-date with the latest best practices. It works with some of the most popular IDE/Text-Editor such as VS Code, PyCharm, Sublime and Vim.

> 💡 You can also install Sourcery to your GitHub repos

#### Benefits of [Sourcery](https://sourcery.ai/invite/kqMdSInZ)

1.  **_Improves code quality_**: [Sourcery](https://sourcery.ai/invite/kqMdSInZ) analyzes your code and generates suggestions for improvement based on best practices and industry standards. This helps you write cleaner, more maintainable code.
2.  **_Increases efficiency:_** By automating repetitive tasks and catching errors early, [Sourcery](https://sourcery.ai/invite/kqMdSInZ) saves you time and effort in the long run. You can focus on writing new code instead of fixing old code.
3.  **_Encourages code consistency_**: By enforcing consistent coding styles, [Sourcery](https://sourcery.ai/invite/kqMdSInZ) helps to keep your codebase organized and easy to read. This makes it easier for others to understand and contribute to your code.
4.  **_Enhances development workflow:_** [Sourcery](https://sourcery.ai/invite/kqMdSInZ) integrates seamlessly with your existing development tools and workflows, making it easy to use and implement.

#### How to Use [Sourcery](https://sourcery.ai/invite/kqMdSInZ)

[Sourcery](https://sourcery.ai/invite/kqMdSInZ) is easy to set up and use. Here’s how you can get started:

1.  Install the [Sourcery](https://sourcery.ai/invite/kqMdSInZ) package from PyPI using pip or your preferred package manager.
2.  Create a configuration file in your project directory, which defines the rules that [Sourcery](https://sourcery.ai/invite/kqMdSInZ) will follow when analyzing your code.
3.  Run Sourcery in your project directory to analyze your code and generate suggested improvements.

#### Installation

[Sourcery](https://sourcery.ai/invite/kqMdSInZ) can be installed via pip:

pip install sourcery

After installation, you can run Sourcery in your project directory to analyze your code and generate new files with proposed improvements.

#### Code Examples

Here are a few examples of how Sourcery can improve your Python code:

1\. Type hints: Sourcery can automatically add type hints to your code, making it easier for others to understand what each variable represents. This also makes it easier to catch type errors before they become a problem.  
2\. Automatic documentation: Sourcery can automatically generate documentation for your code, saving you time and effort. This makes it easier for others to understand how your code works and what it does.  
3\. Exception handling: Sourcery can help you catch and handle exceptions more effectively, improving the stability and reliability of your code.  
4\. Code refactoring: Sourcery can recommend changes to your code that make it more readable and maintainable. This can help you write better code that is easier to understand and modify in the future.  
  
**Example 1**  
Here’s an example of a code refactoring that Sourcery can perform:

Suppose you have the following code that calculates the factorial of a given number:

def factorial(n):  
if n == 0:  
  return 1  
else:  
 return n \* factorial(n-1)

While this code works, it can be improved in terms of readability and maintainability. For example, the function could benefit from adding a docstring and using a more descriptive variable name.

Sourcery can automatically perform these improvements for you with just one command. After running Sourcery, you might see the following updated code:

def factorial(num: int) -> int:  
  """Calculate the factorial of a given number.  
  Args:  
  num (int): The number to calculate the factorial of.  
  Returns:  
   int: The factorial of the given number.  
 """  
  if num == 0:  
   return 1  
 else:  
   return num \* factorial(num - 1)

As you can see, Sourcery has added a docstring to the function, indicating what the function does and what it returns. It has also added type hints to the parameters and return value, making the function easier to understand and use. These small improvements can make a big difference in the readability and maintainability of your code.

**Example 2**  
Here’s an example of how Sourcery can refactor a long nested loop into a more concise and efficient list comprehension:

Suppose you have the following code that creates a list of squares for a given range of numbers:

def create\_square\_list(start, end):  
  squares = \[\]  
  for i in range(start, end + 1):  
    for j in range(i):  
      squares.append(j \*\* 2)  
  return squares

While this code works, it can be improved in terms of readability and efficiency. By using a list comprehension, we can simplify the code and make it run faster.

[Sourcery](https://sourcery.ai/invite/kqMdSInZ) can perform this optimization for you with just one command. After running [Sourcery](https://sourcery.ai/invite/kqMdSInZ), you might see the following updated code:

def create\_square\_list(start, end):  
  """Create a list of squares for a given range of numbers.  
  
  Args:  
   start (int): The start of the range.  
   end (int): The end of the range.  
  
  Returns:  
 list: A list of squares for the given range.  
 """  
 return \[j \*\* 2 for i in range(start, end + 1) for j in range(i)\]

As you can see, [Sourcery](https://sourcery.ai/invite/kqMdSInZ) has transformed the nested loops into a single list comprehension, making the code more concise and efficient. This small optimization can make a big difference in the performance of your code, especially when dealing with large data sets.

You also can hoover over your function and get a metrics on your code such as size, complexity, working memory and a quality score:

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1676019511452/ba2ab955-c72c-4417-baef-a695fa47ed40.png)

#### Conclusion

[Sourcery](https://sourcery.ai/invite/kqMdSInZ) is a powerful tool that helps you write better Python code. Whether you’re a seasoned developer or just starting out, [Sourcery](https://sourcery.ai/invite/kqMdSInZ) can help you write code that is cleaner, more maintainable, and easier to understand. So why wait? Give [Sourcery](https://sourcery.ai/invite/kqMdSInZ) a try today and start writing better Python code!

_More content at_ [**_PlainEnglish.io_**](https://plainenglish.io/)_._

_Sign up for our_ [**_free weekly newsletter_**](http://newsletter.plainenglish.io/)_. Follow us on_ [**_Twitter_**](https://twitter.com/inPlainEngHQ), [**_LinkedIn_**](https://www.linkedin.com/company/inplainenglish/)**_,_** [**_YouTube_**](https://www.youtube.com/channel/UCtipWUghju290NWcn8jhyAw)**_, and_** [**_Discord_**](https://discord.com/invite/GtDtUAvyhW)**_._**

**_Build awareness and adoption for your tech startup with_** [**_Circuit_**](https://circuit.ooo/?utm=publication-post-cta)_._

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1676019511884/82f34f9a-201c-4822-97fb-0d3f50a1fb83.gif)

* * *

[Sourcery: A Free Tool for Better Python Code!](https://python.plainenglish.io/sourcery-a-free-tool-for-better-python-code-ef37e2fb791) was originally published in [Python in Plain English](https://python.plainenglish.io) on Medium, where people are continuing the conversation by highlighting and responding to this story.