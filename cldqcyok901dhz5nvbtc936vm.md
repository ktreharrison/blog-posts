# 5 Python Libraries you need!

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539505556/b9358b6c-ad24-41a2-b7d0-b1967f059e1f.png)

### 5 favorite Python Libraries you need to try!

Python is a popular programming language that has a wide range of libraries and tools available for various tasks. In this article, we’ll take a quick look at five libraries that can be particularly useful for automating tasks, creating cloud infrastructure, formatting code, and managing dependencies.

> **📣 Notes**: **None** of the following library is not a built-in library in Python, so you will need to pip install each library. I have linked the home page of all the libraies.

#### File & Folder Management

Is your desktop disorderly? You are unable to locate anything in your documents and downloads. Is it too time-consuming to manually sort and rename all of these files? It’s time to automate it once so you can profit from it always.

[**organize**](https://organize.readthedocs.io/en/latest/): is a Python library that allows you to automate repetitive tasks by writing a simple YAML config file. The library provides a simple command line that makes it easy to interact with the underlying operating system, such as running commands and reading and writing files. This can save a lot of time and effort, especially when working with large amounts of data or when performing tasks that need to be done frequently.

Here is an example of the YAML file

rules:  
  - name: "Find PDFs"  
    locations:  
      - ~/Downloads  
    subfolders: true  
    filters:  
      - extension: pdf  
    actions:  
      - echo: "Found PDF!"  
  

Here is a simulation of how I clean my downloads folders:

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539506307/7dea2d8e-5c18-4f4b-9b60-662efc5022cf.gif)

gif of the organize library cleaning my downloads folder

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539507057/3bdfea74-7f86-4cf9-bbaa-21e87625bede.png)

organize library logo

#### For Cloud Computing

You don’t want to waste time connecting ten AWS services to create a website or backend?

[**pulumi**](https://www.pulumi.com/): pulumi is a Python library that makes it easy to create, update, and manage cloud infrastructure using code. It allows you to write infrastructure as code (IaC) using Python, which can be more efficient and easier to understand than using a web-based interface or a configuration file. With pulumi, you can define your infrastructure using Python classes and methods, and the library will take care of provisioning and updating resources on various cloud providers such as AWS, Azure, Google cloud and more.

You can view a host of examples [**here**](https://github.com/pulumi/examples)**.**

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539507375/a5227e64-a5d0-4f14-8582-f30364cec348.png)

pulumi library logo

#### Code Formatting

Do you want to spend more time focusing on your logic and code solution and less on formatting along the way?

[**black**](https://black.readthedocs.io/en/stable/#): black is a popular Python library that helps you format your code automatically. It can help you to keep your code consistent and easy to read, by automatically applying a set of rules to your code. Black is especially useful when working on large codebases with multiple contributors, as it can help to ensure that everyone’s code looks the same.

[**black has a playground**](https://black.vercel.app/?version=stable&state=_Td6WFoAAATm1rRGAgAhARYAAAB0L-Wj4ARsAnNdAD2IimZxl1N_WlkPinBFoXIfdFTaTVkGVeHShArYj9yPlDvwBA7LhGo8BvRQqDilPtgsfdKl-ha7EFp0Ma6lY_06IceKiVsJ3BpoICJM9wU1VJLD7l3qd5xTmo78LqThf9uibGWcWCD16LBOn0JK8rhhx_Gf2ClySDJtvm7zQJ1Z-Ipmv9D7I_zhjztfi2UTVsJp7917XToHBm2EoNZqyE8homtGskFIiif5EZthHQvvOj8S2gJx8_t_UpWp1ScpIsD_Xq83LX-B956I_EBIeNoGwZZPFC5zAIoMeiaC1jU-sdOHVucLJM_x-jkzMvK8Utdfvp9MMvKyTfb_BZoe0-FAc2ZVlXEpwYgJVAGdCXv3lQT4bpTXyBwDrDVrUeJDivSSwOvT8tlnuMrXoD1Sk2NZB5SHyNmZsfyAEqLALbUnhkX8hbt5U2yNQRDf1LQhuUIOii6k6H9wnDNRnBiQHUfzKfW1CLiThnuVFjlCxQhJ60u67n3EK38XxHkQdOocJXpBNO51E4-f9z2hj0EDTu_ScuqOiC9cI8qJ4grSZIOnnQLv9WPvmCzx5zib3JacesIxMVvZNQiljq_gL7udm1yeXQjENOrBWbfBEkv1P4izWeAysoJgZUhtZFwKFdoCGt2TXe3xQ-wVZFS5KoMPhGFDZGPKzpK15caQOnWobOHLKaL8eFA-qI44qZrMQ7sSLn04bYeenNR2Vxz7hvK0lJhkgKrpVfUnZrtF-e-ubeeUCThWus4jZbKlFBe2Kroz90Elij_UZBMFCcFo0CfIx5mGlrINrTJLhERszRMMDd39XsBDzpZIYV4TcG7HoMS_IF8aMAAAxI-5uTWXbUQAAY8F7QgAAP01Vc6xxGf7AgAAAAAEWVo=) for you to see its magic at work

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539507949/f9c48e7f-92eb-4671-93f4-9b7e833a09b1.png)

black library logo

#### Handling Date & Time

Need a simplify way to handle date and time?

4\. pendulum: pendulum is a library for handling dates and times in Python. It provides a simple and easy-to-use API for working with dates and times, and it is compatible with the datetime module in the Python standard library. The pendulum library provides a lot of additional functionality such as localization and support for time zones, advanced formatting options and more.

Example:

import pendulum  
  
now = pendulum.now("Europe/Paris")  
  
\# Changing timezone  
now.in\_timezone("America/Toronto")  
  
\# Default support for common datetime formats  
now.to\_iso8601\_string()  
  
\# Shifting  
now.add(days=2)

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539508326/aebb4b2e-2a1e-436b-9fd8-75424e7c7f17.png)

Pendulum library logo

#### Dependency Management

Need to manage your package with ease and at scale ?

[**poetry**](https://python-poetry.org/): poetry is a Python dependency management tool that makes it easy to install and manage your Python dependencies. It allows you to declare your dependencies in a single file, and it will handle installing them and creating a virtual environment for your project. Poetry can also be useful for packaging and publishing your own Python packages. It makes the process of creating, publishing and distributing python packages easy and consistent.

[**Here**](https://realpython.com/dependency-management-python-poetry/#add-poetry-to-an-existing-project) is a great article to get you started with poetry

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539508709/e07ed3bb-eec0-4008-8d88-c4abed33c97f.gif)

So to sum up, organize, pulumi, black, pendulum, and poetry are five powerful Python libraries that can help you automate tasks, create and manage cloud infrastructure, format your code, handle dates and time and manage dependencies respectively. They are widely used in many Python projects and have proven to be very effective and useful. If you are looking for ways to make your work easier and more efficient, these libraries can be a great way to get started.

![](https://cdn.hashnode.com/res/hashnode/imageupload/v1675539509713/40bec609-9f84-4549-8c23-0c7a85e35567.gif)

* * *

[5 Python Libraries you need!](https://python.plainenglish.io/5-python-libraries-you-need-54e6867e264) was originally published in [Python in Plain English](https://python.plainenglish.io) on Medium, where people are continuing the conversation by highlighting and responding to this story.