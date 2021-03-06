---
layout: default
title: Tag Developers Guide
---

# bean

Please make sure you have read the [Tag Syntax](tag-syntax.html) document and understand how tag attribute syntax works.

## Description

{% comment %}start snippet id=javadoc|javadoc=true|url=org.apache.struts2.components.Bean {% endcomment %}
<p> <p>Instantiates a class that conforms to the JavaBeans specification. This tag has a body which can contain
 a number of {@link Param} elements to set any mutator methods on that class.</p>

 <p>If the var attribute is set on the BeanTag, it will place the instantiated bean into the
 stack's Context.</p>

</p>
{% comment %}end snippet id=javadoc|javadoc=true|url=org.apache.struts2.components.Bean {% endcomment %}

## Parameters

{% comment %}start snippet id=tagattributes|javadoc=false|url=struts2-tags/bean.html {% endcomment %}
<p>		<table width="100%">

			<tr>

				<td colspan="6"><h4>Dynamic Attributes Allowed:</h4> false</td>

			</tr>

			<tr>

				<td colspan="6">&nbsp;</td>

			</tr>

			<tr>

				<th align="left" valign="top"><h4>Name</h4></th>

				<th align="left" valign="top"><h4>Required</h4></th>

				<th align="left" valign="top"><h4>Default</h4></th>

				<th align="left" valign="top"><h4>Evaluated</h4></th>

				<th align="left" valign="top"><h4>Type</h4></th>

				<th align="left" valign="top"><h4>Description</h4></th>

			</tr>

				<tr>

					<td align="left" valign="top">name</td>

					<td align="left" valign="top"><strong>true</strong></td>

					<td align="left" valign="top"></td>

					<td align="left" valign="top">false</td>

					<td align="left" valign="top">String</td>

					<td align="left" valign="top">The class name of the bean to be instantiated (must respect JavaBean specification)</td>

				</tr>

				<tr>

					<td align="left" valign="top">var</td>

					<td align="left" valign="top">false</td>

					<td align="left" valign="top"></td>

					<td align="left" valign="top">false</td>

					<td align="left" valign="top">String</td>

					<td align="left" valign="top">Name used to reference the value pushed into the Value Stack</td>

				</tr>

		</table>

</p>
{% comment %}end snippet id=tagattributes|javadoc=false|url=struts2-tags/bean.html {% endcomment %}

## Examples

{% comment %}start snippet id=examples|javadoc=true|lang=xml|url=org.apache.struts2.components.Bean {% endcomment %}

```xml
 <-- in freemarker form -->
 [@s.bean name="org.apache.struts2.example.counter.SimpleCounter" var="counter"]
   [s:param name="foo" value="BAR"/]
   The value of foo is : [s:property value="foo"/], when inside the bean tag.
 [/s:bean]

 <-- in jsp form -->
 <s:bean name="org.apache.struts2.example.counter.SimpleCounter" var="counter">
   <s:param name="foo" value="BAR" />
   The value of foot is : <s:property value="foo"/>, when inside the bean tag <br />
 </s:bean>

```

{% comment %}end snippet id=examples|javadoc=true|lang=xml|url=org.apache.struts2.components.Bean {% endcomment %}

{% comment %}start snippet id=examplesdescription|javadoc=true|url=org.apache.struts2.components.Bean {% endcomment %}
<p> <p>This example instantiates a bean called SimpleCounter and sets the foo property (setFoo('BAR')). The
 SimpleCounter object is then pushed onto the Valuestack, which means that we can call its accessor methods (getFoo())
 with the Property tag and get their values.</p>

 <p>In the above example, the id has been set to a value of <i>counter</i>. This means that the SimpleCounter class
 will be placed into the stack's context. You can access the SimpleCounter class using a Struts tag:</p>

 <pre>
 <-- jsp form -->
 <s:property value="#counter" />

 <-- freemarker form -->
 [s:property value="#counter.foo"/]
 </pre>

 <p>In the property tag example, the <i>#</i> tells Ognl to search the context for the SimpleCounter class which has
 an id(key) of <i>counter</i></p>
</p>
{% comment %}end snippet id=examplesdescription|javadoc=true|url=org.apache.struts2.components.Bean {% endcomment %}
