---
layout: post
title:  "Razor Pages With Entity Tutorial Pitfalls"
date:   2018-09-23 21:10:00 -0500
categories: 
    - ASP.NET Core 2
---
*Note: This is referring to the tutorial found [here][tutorial-link]. Also, I'm using the .NET Core CLI in a Linux environment.* 

In this post I will be adding any pitfalls I run into when following the tutorial.

## Scaffolding Models

In the Section titled **Scaffold the student model**, after adding the required package, an error will be thrown when trying to run the following command.

{% highlight bash %}
dotnet aspnet-codegenerator razorpage -m Student -dc ContosoUniversity.Models.SchoolContext -udl -outDir Pages/Students --referenceScriptLibraries
{% endhighlight %}

I actually had to go into the csproj and add the following, below the Item Group with the package references.

{% highlight xml %}
<ItemGroup>  
    <DotNetCliToolReference Include="Microsoft.VisualStudio.Web.CodeGeneration.Tools" Version="2.0.0" />  
</ItemGroup>
{% endhighlight %}

Also, if you're on Linux you'll have to change `Pages\Students` in the actual scaffold command, provided in the tutorial, to `Pages/Students`.

[tutorial-link]: https://docs.microsoft.com/en-us/aspnet/core/data/ef-rp/intro?view=aspnetcore-2.1&tabs=netcore-cli
