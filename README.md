# java.sonar.rules
java sonar rules


## 1.


*  Insufficient comment density

system_tags : null, priority : 2; plugin_rule_key : InsufficientCommentDensity

<h5>An issue is created on a file as soon as the comment density coverage on this file is less than the required threshold. It gives the number of comment lines to be written in order to reach the required threshold.</h5>

--------



## 2.


*  Duplicated blocks

system_tags : null, priority : 2; plugin_rule_key : DuplicatedBlocks

<h5>An issue is created on a file as soon as there is a block of duplicated code on this file. It gives the number of blocks in the file.</h5>

--------



## 3.


*  Skipped unit tests

system_tags : null, priority : 2; plugin_rule_key : SkippedUnitTests

<h5>Skipped unit tests are considered as dead code. Either they should be activated again (and updated) or they should be removed.</h5>

--------



## 4.


*  Insufficient line coverage by unit tests

system_tags : null, priority : 2; plugin_rule_key : InsufficientLineCoverage

<h5>An issue is created on a file as soon as the line coverage on this file is less than the required threshold. It gives the number of lines to be covered in order to reach the required threshold.</h5>

--------



## 5.


*  Failed unit tests

system_tags : null, priority : 2; plugin_rule_key : FailedUnitTests

<h5>Test failures or errors generally indicate that regressions have been introduced. Those tests should be handled as soon as possible to reduce the cost to fix the corresponding regressions.</h5>

--------



## 6.


*  Insufficient branch coverage by unit tests

system_tags : null, priority : 2; plugin_rule_key : InsufficientBranchCoverage

<h5>An issue is created on a file as soon as the branch coverage on this file is less than the required threshold.It gives the number of branches to be covered in order to reach the required threshold.</h5>

--------



## 7.


*  Field names should start with a lower case letter

system_tags : null, priority : 2; plugin_rule_key : NM_FIELD_NAMING_CONVENTION

<h5>
      Names of fields that are not final should be in mixed case 
      with a lowercase first letter and the first letters of subsequent words capitalized.
      </h5>

--------



## 8.


*  Negating the result of compareTo()/compare()

system_tags : null, priority : 1; plugin_rule_key : RV_NEGATING_RESULT_OF_COMPARETO

<h5>This code negatives the return value of a compareTo or compare method. This is a questionable or bad 
programming practice, since if the return value is Integer.MIN_VALUE, negating the return value won't 
negate the sign of the result. You can achieve the same intended result by reversing the order of the 
operands rather than by negating the results.</h5>

--------



## 9.


*  Bad practice - Equals checks for noncompatible operand

system_tags : null, priority : 2; plugin_rule_key : EQ_CHECK_FOR_OPERAND_NOT_COMPATIBLE_WITH_THIS

<h5> This equals method is checking to see if the argument is some incompatible type
(i.e., a class that is neither a supertype nor subtype of the class that defines
the equals method). For example, the Foo class might have an equals method
that looks like:

<p><code><pre>
public boolean equals(Object o) {
  if (o instanceof Foo)
    return name.equals(((Foo)o).name);
  else if (o instanceof String)
    return name.equals(o);
  else return false;
</pre></code></h5>

<p>This is considered bad practice, as it makes it very hard to implement an equals method that
is symmetric and transitive. Without those properties, very unexpected behavoirs are possible.
</p>

--------



## 10.


*  Correctness - Value that might carry a type qualifier is always used in a way prohibits it from having that type qualifier

system_tags : null, priority : 3; plugin_rule_key : TQ_MAYBE_SOURCE_VALUE_REACHES_NEVER_SINK

<h5>
      A value that is annotated as possibility being an instance of
	the values denoted by the type qualifier, and the value is guaranteed to be used
	in a way that prohibits values denoted by that type qualifier.
      </h5>

--------



## 11.


*  Correctness - Format string placeholder incompatible with passed argument

system_tags : null, priority : 3; plugin_rule_key : VA_FORMAT_STRING_BAD_ARGUMENT

<h5>
The format string placeholder is incompatible with the corresponding
argument. For example,
<code>
  System.out.println("%d\n", "hello");
</code>
<p>The %d placeholder requires a numeric argument, but a string value is
passed instead. 
A runtime exception will occur when 
this statement is executed.
</h5>

--------



## 12.


*  Performance - Private method is never called

system_tags : null, priority : 3; plugin_rule_key : UPM_UNCALLED_PRIVATE_METHOD

<h5> This private method is never called. Although it is
possible that the method will be invoked through reflection,
it is more likely that the method is never used, and should be
removed.
</h5>

<p>
This rule is deprecated, use {rule:squid:UnusedPrivateMethod} instead.
</p>

--------



## 13.


*  Dodgy - Thread passed where Runnable expected

system_tags : null, priority : 2; plugin_rule_key : DMI_THREAD_PASSED_WHERE_RUNNABLE_EXPECTED

<h5> A Thread object is passed as a parameter to a method where 
a Runnable is expected. This is rather unusual, and may indicate a logic error
or cause unexpected behavior.
   </h5>

--------



## 14.


*  Unchecked/unconfirmed cast of return value from method

system_tags : null, priority : 3; plugin_rule_key : BC_UNCONFIRMED_CAST_OF_RETURN_VALUE

<h5>
This code performs an unchecked cast of the return value of a method.
The code might be calling the method in such a way that the cast is guaranteed to be
safe, but FindBugs is unable to verify that the cast is safe.  Check that your program logic ensures that this
cast will not fail.
</h5>

--------



## 15.


*  Multithreaded correctness - A volatile reference to an array doesn't treat the array elements as volatile

system_tags : null, priority : 2; plugin_rule_key : VO_VOLATILE_REFERENCE_TO_ARRAY

<h5>This declares a volatile reference to an array, which might not be what
you want. With a volatile reference to an array, reads and writes of
the reference to the array are treated as volatile, but the array elements
are non-volatile. To get volatile array elements, you will need to use
one of the atomic array classes in java.util.concurrent (provided
in Java 5.0).</h5>

--------



## 16.


*  Performance - Method invokes inefficient Number constructor; use static valueOf instead

system_tags : null, priority : 3; plugin_rule_key : DM_NUMBER_CTOR

<h5>
      Using <code>new Integer(int)</code> is guaranteed to always result in a new object whereas
      <code>Integer.valueOf(int)</code> allows caching of values to be done by the compiler, class library, or JVM.
      Using of cached values avoids object allocation and the code will be faster.
      </h5>
      <p>
      Values between -128 and 127 are guaranteed to have corresponding cached instances
      and using <code>valueOf</code> is approximately 3.5 times faster than using constructor.
      For values outside the constant range the performance of both styles is the same.
      </p>
      <p>
      Unless the class must be compatible with JVMs predating Java 1.5,
      use either autoboxing or the <code>valueOf()</code> method when creating instances of
      <code>Long</code>, <code>Integer</code>, <code>Short</code>, <code>Character</code>, and <code>Byte</code>.
      </p>

--------



## 17.


*  Dodgy - Redundant nullcheck of value known to be null

system_tags : null, priority : 3; plugin_rule_key : RCN_REDUNDANT_NULLCHECK_OF_NULL_VALUE

<h5> This method contains a redundant check of a known null value against
the constant null.</h5>

--------



## 18.


*  Correctness - TestCase defines tearDown that doesn't call super.tearDown()

system_tags : null, priority : 3; plugin_rule_key : IJU_TEARDOWN_NO_SUPER

<h5> Class is a JUnit TestCase and implements the tearDown method. The tearDown method should call
super.tearDown(), but doesn't.</h5>

--------



## 19.


*  Performance - Method allocates a boxed primitive just to call toString

system_tags : null, priority : 2; plugin_rule_key : DM_BOXED_PRIMITIVE_TOSTRING

<h5>A boxed primitive is allocated just to call toString(). It is more effective to just use the static
  form of toString which takes the primitive value. So,</h5>
  <table>
     <tr><th>Replace...</th><th>With this...</th></tr>
     <tr><td>new Integer(1).toString()</td><td>Integer.toString(1)</td></tr>
     <tr><td>new Long(1).toString()</td><td>Long.toString(1)</td></tr>
     <tr><td>new Float(1.0).toString()</td><td>Float.toString(1.0)</td></tr>
     <tr><td>new Double(1.0).toString()</td><td>Double.toString(1.0)</td></tr>
     <tr><td>new Byte(1).toString()</td><td>Byte.toString(1)</td></tr>
     <tr><td>new Short(1).toString()</td><td>Short.toString(1)</td></tr>
     <tr><td>new Boolean(true).toString()</td><td>Boolean.toString(true)</td></tr>
  </table>

--------



## 20.


*  Class defines equal(Object); should it be equals(Object)?

system_tags : null, priority : 3; plugin_rule_key : NM_BAD_EQUAL

<h5>
      This class defines a method <code>equal(Object)</code>.  
      This method does not override the <code>equals(Object)</code> method 
      in <code>java.lang.Object</code>, which is probably what was intended.
      </h5>

--------



## 21.


*  Correctness - TestCase implements a non-static suite method

system_tags : null, priority : 3; plugin_rule_key : IJU_SUITE_NOT_STATIC

<h5> Class is a JUnit TestCase and implements the suite() method.
 The suite method should be declared as being static, but isn't.</h5>

--------



## 22.


*  Bad practice - Class defines hashCode() and uses Object.equals()

system_tags : null, priority : 3; plugin_rule_key : HE_HASHCODE_USE_OBJECT_EQUALS

<h5> This class defines a <code>hashCode()</code> method but inherits its
  <code>equals()</code> method from <code>java.lang.Object</code>
  (which defines equality by comparing object references).&nbsp; Although
  this will probably satisfy the contract that equal objects must have
  equal hashcodes, it is probably not what was intended by overriding
  the <code>hashCode()</code> method.&nbsp; (Overriding <code>hashCode()</code>
  implies that the object's identity is based on criteria more complicated
  than simple reference equality.)</h5>
<p>If you don't think instances of this class will ever be inserted into a HashMap/HashTable,
the recommended <code>hashCode</code> implementation to use is:</p>
<p><pre>public int hashCode() {
  assert false : "hashCode not designed";
  return 42; // any arbitrary constant will do
  }</pre></p>

<p>
This rule is deprecated, use {rule:squid:S1206} instead.
</p>

--------



## 23.


*  Correctness - Integer multiply of result of integer remainder

system_tags : null, priority : 3; plugin_rule_key : IM_MULTIPLYING_RESULT_OF_IREM

<h5>
The code multiplies the result of an integer remaining by an integer constant.
Be sure you don't have your operator precedence confused. For example
i % 60 * 1000 is (i % 60) * 1000, not i % (60 * 1000).
</h5>

--------



## 24.


*  Bad practice - Method ignores results of InputStream.skip()

system_tags : null, priority : 2; plugin_rule_key : SR_NOT_CHECKED

<h5> This method ignores the return value of
  <code>java.io.InputStream.skip()</code> which can skip multiple bytes.&nbsp;
  If the return value is not checked, the caller will not be able to correctly
  handle the case where fewer bytes were skipped than the caller requested.&nbsp;
  This is a particularly insidious kind of bug, because in many programs,
  skips from input streams usually do skip the full amount of data requested,
  causing the program to fail only sporadically. With Buffered streams, however,
  skip() will only skip data in the buffer, and will routinely fail to skip the
  requested number of bytes.</h5>

--------



## 25.


*  Dodgy - Method uses the same code for two switch clauses

system_tags : null, priority : 3; plugin_rule_key : DB_DUPLICATE_SWITCH_CLAUSES

<h5>
      This method uses the same code to implement two clauses of a switch statement.
	This could be a case of duplicate code, but it might also indicate
	a coding mistake.
      </h5>

--------



## 26.


*  Correctness - Non-virtual method call passes null for nonnull parameter

system_tags : null, priority : 3; plugin_rule_key : NP_NULL_PARAM_DEREF_NONVIRTUAL

<h5>
      A possibly-null value is passed to a nonnull method parameter.
	Either the parameter is annotated as a parameter that should
	always be nonnull, or analysis has shown that it will always be 
	dereferenced.
      </h5>

--------



## 27.


*  Method tightens nullness annotation on parameter

system_tags : null, priority : 2; plugin_rule_key : NP_METHOD_PARAMETER_TIGHTENS_ANNOTATION

<h5>
A method should always implement the contract of a method it overrides. Thus, if a method takes a parameter
that is marked as @Nullable, you shouldn't override that method in a subclass with a method where that parameter is @Nonnull.
Doing so violates the contract that the method should handle a null parameter.
</h5>

--------



## 28.


*  Correctness - Method ignores return value

system_tags : null, priority : 1; plugin_rule_key : RV_RETURN_VALUE_IGNORED

<h5> The return value of this method should be checked. One common
cause of this warning is to invoke a method on an immutable object,
thinking that it updates the object. For example, in the following code
fragment,</h5>
<blockquote>
<pre>
String dateString = getHeaderField(name);
dateString.trim();
</pre>
</blockquote>
<p>the programmer seems to be thinking that the trim() method will update
the String referenced by dateString. But since Strings are immutable, the trim()
function returns a new String value, which is being ignored here. The code
should be corrected to: </p>
<blockquote>
<pre>
String dateString = getHeaderField(name);
dateString = dateString.trim();
</pre>
</blockquote>

--------



## 29.


*  Correctness - Exception created and dropped rather than thrown

system_tags : null, priority : 3; plugin_rule_key : RV_EXCEPTION_NOT_THROWN

<h5> This code creates an exception (or error) object, but doesn't do anything with it. For example,
something like </h5>
<blockquote>
<pre>
if (x &lt; 0)
  new IllegalArgumentException("x must be nonnegative");
</pre>
</blockquote>
<p>It was probably the intent of the programmer to throw the created exception:</p>
<blockquote>
<pre>
if (x &lt; 0)
  throw new IllegalArgumentException("x must be nonnegative");
</pre>
</blockquote>

--------



## 30.


*  Bad practice - Classloaders should only be created inside doPrivileged block

system_tags : null, priority : 2; plugin_rule_key : DP_CREATE_CLASSLOADER_INSIDE_DO_PRIVILEGED

<h5> This code creates a classloader,  which requires a security manager.
  If this code will be granted security permissions, but might be invoked by code that does not
  have security permissions, then the classloader creation needs to occur inside a doPrivileged block.</h5>

--------



## 31.


*  Field isn't final but should be refactored to be so

system_tags : null, priority : 2; plugin_rule_key : MS_SHOULD_BE_REFACTORED_TO_BE_FINAL

<h5>
This static field public but not final, and
could be changed by malicious code or
by accident from another package.
The field could be made final to avoid
this vulnerability. However, the static initializer contains more than one write
to the field, so doing so will require some refactoring.
</h5>

--------



## 32.


*  Internationalization - Consider using Locale parameterized version of invoked method

system_tags : null, priority : 0; plugin_rule_key : DM_CONVERT_CASE

<h5> A String is being converted to upper or lowercase, using the platform's default encoding. This may
      result in improper conversions when used with international characters. Use the </h5>
      <table><tr><td>String.toUpperCase( Locale l )</td></tr><tr><td>String.toLowerCase( Locale l )</td></tr></table>
      <p>versions instead.</p>

--------



## 33.


*  Dodgy - Vacuous comparison of integer value

system_tags : null, priority : 3; plugin_rule_key : INT_VACUOUS_COMPARISON

<h5> There is an integer comparison that always returns
the same value (e.g., x &lt;= Integer.MAX_VALUE).
</h5>

--------



## 34.


*  Malicious code vulnerability - Field should be both final and package protected

system_tags : null, priority : 2; plugin_rule_key : MS_FINAL_PKGPROTECT

<h5>
   A mutable static field could be changed by malicious code or
        by accident from another package.
        The field could be made package protected and/or made final
   to avoid
        this vulnerability.</h5>

--------



## 35.


*  Don't reuse entry objects in iterators

system_tags : null, priority : 2; plugin_rule_key : PZ_DONT_REUSE_ENTRY_OBJECTS_IN_ITERATORS

<h5>The entrySet() method is allowed to return a view of the underlying Map in which an <code>Iterator</code> 
and <code>Map.Entry</code>. This clever idea was used in several Map implementations, but introduces the possibility of
 nasty coding mistakes. If a map m returns such an iterator for an entrySet, then <code>c.addAll(m.entrySet())</code> will 
 go badly wrong. All of the Map implementations in OpenJDK 1.7 have been rewritten to avoid this, you should to.</h5>

--------



## 36.


*  Correctness - Value that might not carry a type qualifier is always used in a way requires that type qualifier

system_tags : null, priority : 3; plugin_rule_key : TQ_MAYBE_SOURCE_VALUE_REACHES_ALWAYS_SINK

<h5>
      A value that is annotated as possibility not being an instance of
	the values denoted by the type qualifier, and the value is guaranteed to be used
	in a way that requires values denoted by that type qualifier.
      </h5>

--------



## 37.


*  Bad practice - Random object created and used only once

system_tags : null, priority : 3; plugin_rule_key : DMI_RANDOM_USED_ONLY_ONCE

<h5> This code creates a java.util.Random object, uses it to generate one random number, and then discards
the Random object. This produces mediocre quality random numbers and is inefficient. 
If possible, rewrite the code so that the Random object is created once and saved, and each time a new random number
is required invoke a method on the existing Random object to obtain it.
</h5>

<p>If it is important that the generated Random numbers not be guessable, you <em>must</em> not create a new Random for each random
number; the values are too easily guessable. You should strongly consider using a java.security.SecureRandom instead
(and avoid allocating a new SecureRandom for each random number needed).
</p>

--------



## 38.


*  Performance - Primitive value is boxed then unboxed to perform primitive coercion

system_tags : null, priority : 2; plugin_rule_key : BX_BOXING_IMMEDIATELY_UNBOXED_TO_PERFORM_COERCION

<h5>A primitive boxed value constructed and then immediately converted into a different primitive type
(e.g., <code>new Double(d).intValue()</code>). Just perform direct primitive coercion (e.g., <code>(int) d</code>).</h5>

--------



## 39.


*  Correctness - Check for sign of bitwise operation

system_tags : null, priority : 3; plugin_rule_key : BIT_SIGNED_CHECK_HIGH_BIT

<h5> This method compares an expression such as
<pre>((event.detail &amp; SWT.SELECTED) &gt; 0)</pre>.
Using bit arithmetic and then comparing with the greater than operator can
lead to unexpected results (of course depending on the value of
SWT.SELECTED). If SWT.SELECTED is a negative number, this is a candidate
for a bug. Even when SWT.SELECTED is not negative, it seems good practice
to use '!= 0' instead of '&gt; 0'.
</h5>
<p>
<em>Boris Bokowski</em>
</p>

--------



## 40.


*  Dodgy - Method checks to see if result of String.indexOf is positive

system_tags : null, priority : 1; plugin_rule_key : RV_CHECK_FOR_POSITIVE_INDEXOF

<h5> The method invokes String.indexOf and checks to see if the result is positive or non-positive.
   It is much more typical to check to see if the result is negative or non-negative. It is
   positive only if the substring checked for occurs at some place other than at the beginning of
   the String.</h5>

--------



## 41.


*  Dodgy - Invocation of substring(0), which returns the original value

system_tags : null, priority : 3; plugin_rule_key : DMI_USELESS_SUBSTRING

<h5>
This code invokes substring(0) on a String, which returns the original value.
</h5>

--------



## 42.


*  Multithreaded correctness - Monitor wait() called on Condition

system_tags : null, priority : 2; plugin_rule_key : DM_MONITOR_WAIT_ON_CONDITION

<h5>
      This method calls <code>wait()</code> on a
      <code>java.util.concurrent.locks.Condition</code> object.&nbsp;
      Waiting for a <code>Condition</code> should be done using one of the <code>await()</code>
      methods defined by the <code>Condition</code> interface.
      </h5>

--------



## 43.


*  Dodgy - Load of known null value

system_tags : null, priority : 3; plugin_rule_key : NP_LOAD_OF_KNOWN_NULL_VALUE

<h5> The variable referenced at this point is known to be null due to an earlier
   check against null. Although this is valid, it might be a mistake (perhaps you
intended to refer to a different variable, or perhaps the earlier check to see if the
variable is null should have been a check to see if it was nonnull).
</h5>

--------



## 44.


*  Correctness - equals method overrides equals in superclass and may not be symmetric

system_tags : null, priority : 2; plugin_rule_key : EQ_OVERRIDING_EQUALS_NOT_SYMMETRIC

<h5> This class defines an equals method that overrides an equals method in a superclass. Both equals methods
methods use <code>instanceof</code> in the determination of whether two objects are equal. This is fraught with peril,
since it is important that the equals method is symmetrical (in other words, <code>a.equals(b) == b.equals(a)</code>).
If B is a subtype of A, and A's equals method checks that the argument is an instanceof A, and B's equals method
checks that the argument is an instanceof B, it is quite likely that the equivalence relation defined by these
methods is not symmetric.
</h5>

--------



## 45.


*  Correctness - Call to equals() comparing different interface types

system_tags : null, priority : 3; plugin_rule_key : EC_UNRELATED_INTERFACES

<h5> This method calls equals(Object) on two references of unrelated
interface types, where neither is a subtype of the other,
and there are no known non-abstract classes which implement both interfaces.
Therefore, the objects being compared
are unlikely to be members of the same class at runtime
(unless some application classes were not analyzed, or dynamic class
loading can occur at runtime).
According to the contract of equals(),
objects of different
classes should always compare as unequal; therefore, according to the
contract defined by java.lang.Object.equals(Object),
the result of this comparison will always be false at runtime.
</h5>

--------



## 46.


*  Performance - Method invokes inefficient floating-point Number constructor; use static valueOf instead

system_tags : null, priority : 2; plugin_rule_key : DM_FP_NUMBER_CTOR

<h5>
      Using <code>new Double(double)</code> is guaranteed to always result in a new object whereas
      <code>Double.valueOf(double)</code> allows caching of values to be done by the compiler, class library, or JVM.
      Using of cached values avoids object allocation and the code will be faster.
      </h5>
      <p>
      Unless the class must be compatible with JVMs predating Java 1.5,
      use either autoboxing or the <code>valueOf()</code> method when creating instances of <code>Double</code> and <code>Float</code>.
      </p>

--------



## 47.


*  Bad practice - Comparator doesn't implement Serializable

system_tags : null, priority : 2; plugin_rule_key : SE_COMPARATOR_SHOULD_BE_SERIALIZABLE

<h5> This class implements the <code>Comparator</code> interface. You
should consider whether or not it should also implement the <code>Serializable</code>
interface. If a comparator is used to construct an ordered collection
such as a <code>TreeMap</code>, then the <code>TreeMap</code>
will be serializable only if the comparator is also serializable.
As most comparators have little or no state, making them serializable
is generally easy and good defensive programming.
</h5>

--------



## 48.


*  Bad practice - Method might ignore exception

system_tags : null, priority : 2; plugin_rule_key : DE_MIGHT_IGNORE

<h5> This method might ignore an exception.&nbsp; In general, exceptions
  should be handled or reported in some way, or they should be thrown
  out of the method.</h5>

--------



## 49.


*  Correctness - Bad constant value for month

system_tags : null, priority : 3; plugin_rule_key : DMI_BAD_MONTH

<h5>
This code passes a constant month
value outside the expected range of 0..11 to a method.
</h5>

--------



## 50.


*  Bad practice - Finalizer does not call superclass finalizer

system_tags : null, priority : 2; plugin_rule_key : FI_MISSING_SUPER_CALL

<h5> This <code>finalize()</code> method does not make a call to its
  superclass's <code>finalize()</code> method.&nbsp; So, any finalizer
  actions defined for the superclass will not be performed.&nbsp;
  Add a call to <code>super.finalize()</code>.</h5>

--------



## 51.


*  Correctness - TestCase defines setUp that doesn't call super.setUp()

system_tags : null, priority : 3; plugin_rule_key : IJU_SETUP_NO_SUPER

<h5> Class is a JUnit TestCase and implements the setUp method. The setUp method should call
super.setUp(), but doesn't.</h5>

--------



## 52.


*  Experimental - Test for circular dependencies among classes

system_tags : null, priority : 0; plugin_rule_key : CD_CIRCULAR_DEPENDENCY

<h5>
      This class has a circular dependency with other classes. This makes building these classes
      difficult, as each is dependent on the other to build correctly. Consider using interfaces
      to break the hard dependency.
      </h5>

--------



## 53.


*  Correctness - Method attempts to access a prepared statement parameter with index 0

system_tags : null, priority : 3; plugin_rule_key : SQL_BAD_PREPARED_STATEMENT_ACCESS

<h5> A call to a setXXX method of a prepared statement was made where the
parameter index is 0. As parameter indexes start at index 1, this is always a mistake.</h5>

--------



## 54.


*  Dodgy - Unusual equals method

system_tags : null, priority : 1; plugin_rule_key : EQ_UNUSUAL

<h5> This class doesn't do any of the patterns we recognize for checking that the type of the argument 
is compatible with the type of the <code>this</code> object. There might not be anything wrong with
this code, but it is worth reviewing.
</h5>

--------



## 55.


*  Dodgy - Transient field of class that isn't Serializable.

system_tags : null, priority : 2; plugin_rule_key : SE_TRANSIENT_FIELD_OF_NONSERIALIZABLE_CLASS

<h5> The field is marked as transient, but the class isn't Serializable, so marking it as transient
has absolutely no effect. 
This may be leftover marking from a previous version of the code in which the class was transient, or
it may indicate a misunderstanding of how serialization works.
</h5>

--------



## 56.


*  Correctness - Use of class without a hashCode() method in a hashed data structure

system_tags : null, priority : 3; plugin_rule_key : HE_USE_OF_UNHASHABLE_CLASS

<h5> A class defines an equals(Object)  method but not a hashCode() method,
and thus doesn't fulfill the requirement that equal objects have equal hashCodes.
An instance of this class is used in a hash data structure, making the need to
fix this problem of highest importance.

--------



## 57.


*  Correctness - Value required to have type qualifier, but marked as unknown

system_tags : null, priority : 3; plugin_rule_key : TQ_EXPLICIT_UNKNOWN_SOURCE_VALUE_REACHES_ALWAYS_SINK

<h5>
      A value is used in a way that requires it to be always be a value denoted by a type qualifier, but
	there is an explicit annotation stating that it is not known where the value is required to have that type qualifier.
	Either the usage or the annotation is incorrect.
      </h5>

--------



## 58.


*  Bad comparison of int value with long constant

system_tags : null, priority : 2; plugin_rule_key : INT_BAD_COMPARISON_WITH_INT_VALUE

<h5>This code compares an int value with a long constant that is outside the range of values that can
 be represented as an int value. This comparison is vacuous and possibily to be incorrect.</h5>

--------



## 59.


*  Bad practice - Fields of immutable classes should be final

system_tags : null, priority : 1; plugin_rule_key : JCIP_FIELD_ISNT_FINAL_IN_IMMUTABLE_CLASS

<h5> The class is annotated with net.jcip.annotations.Immutable, and the rules for that annotation require
that all fields are final.
   .</h5>

--------



## 60.


*  Correctness - Covariant equals() method defined, Object.equals(Object) inherited

system_tags : null, priority : 2; plugin_rule_key : EQ_SELF_USE_OBJECT

<h5> This class defines a covariant version of the <code>equals()</code>
  method, but inherits the normal <code>equals(Object)</code> method
  defined in the base <code>java.lang.Object</code> class.&nbsp;
  The class should probably define a <code>boolean equals(Object)</code> method.
  </h5>

<p>
This rule is deprecated, use {rule:squid:S1201} instead.
</p>

--------



## 61.


*  Dodgy - Redundant nullcheck of value known to be non-null

system_tags : null, priority : 3; plugin_rule_key : RCN_REDUNDANT_NULLCHECK_OF_NONNULL_VALUE

<h5> This method contains a redundant check of a known non-null value against
the constant null.</h5>

--------



## 62.


*  Correctness - instanceof will always return false

system_tags : null, priority : 3; plugin_rule_key : BC_IMPOSSIBLE_INSTANCEOF

<h5>
This instanceof test will always return false. Although this is safe, make sure it isn't
an indication of some misunderstanding or some other logic error.
</h5>

--------



## 63.


*  Bad practice - serialVersionUID isn't final

system_tags : null, priority : 3; plugin_rule_key : SE_NONFINAL_SERIALVERSIONID

<h5> This class defines a <code>serialVersionUID</code> field that is not final.&nbsp;
  The field should be made final
   if it is intended to specify
   the version UID for purposes of serialization.</h5>

--------



## 64.


*  Malicious code vulnerability - May expose internal representation by incorporating reference to mutable object

system_tags : null, priority : 2; plugin_rule_key : EI_EXPOSE_REP2

<h5> This code stores a reference to an externally mutable object into the
  internal representation of the object.&nbsp;
   If instances
   are accessed by untrusted code, and unchecked changes to
   the mutable object would compromise security or other
   important properties, you will need to do something different.
  Storing a copy of the object is better approach in many situations.</h5>

--------



## 65.


*  Dodgy - Remainder of 32-bit signed random integer

system_tags : null, priority : 3; plugin_rule_key : RV_REM_OF_RANDOM_INT

<h5> This code generates a random signed integer and then computes
the remainder of that value modulo another value. Since the random
number can be negative, the result of the remainder operation
can also be negative. Be sure this is intended, and strongly
consider using the Random.nextInt(int) method instead.
</h5>

--------



## 66.


*  Bad practice - Creates an empty jar file entry

system_tags : null, priority : 2; plugin_rule_key : AM_CREATES_EMPTY_JAR_FILE_ENTRY

<h5>The code calls <code>putNextEntry()</code>, immediately
followed by a call to <code>closeEntry()</code>. This results
in an empty JarFile entry. The contents of the entry
should be written to the JarFile between the calls to
<code>putNextEntry()</code> and
<code>closeEntry()</code>.</h5>

--------



## 67.


*  Correctness - Method call passes null for nonnull parameter

system_tags : null, priority : 3; plugin_rule_key : NP_NULL_PARAM_DEREF

<h5>
      This method call passes a null value for a nonnull method parameter.
	Either the parameter is annotated as a parameter that should
	always be nonnull, or analysis has shown that it will always be 
	dereferenced.
      </h5>

--------



## 68.


*  Method ignores return value, is this OK?

system_tags : null, priority : 1; plugin_rule_key : RV_RETURN_VALUE_IGNORED_INFERRED

<h5>This code calls a method and ignores the return value. The return value is the same type as the type the 
method is invoked on, and from our analysis it looks like the return value might be important (e.g., like 
ignoring the return value of <code>String.toLowerCase()</code>).
</h5>
<p>We are guessing that ignoring the return value might be a bad idea just from a simple analysis of the 
body of the method. You can use a <code>@CheckReturnValue</code> annotation to instruct FindBugs as to whether 
ignoring the return value of this method is important or acceptable.<p>
<p>Please investigate this closely to decide whether it is OK to ignore the return value. </p>

--------



## 69.


*  Performance - Method invokes inefficient new String(String) constructor

system_tags : null, priority : 2; plugin_rule_key : DM_STRING_CTOR

<h5> Using the <code>java.lang.String(String)</code> constructor wastes memory
  because the object so constructed will be functionally indistinguishable
  from the <code>String</code> passed as a parameter.&nbsp; Just use the
  argument <code>String</code> directly.</h5>

--------



## 70.


*  Bad practice - Class is Serializable, but doesn't define serialVersionUID

system_tags : null, priority : 2; plugin_rule_key : SE_NO_SERIALVERSIONID

<h5> This class implements the <code>Serializable</code> interface, but does
  not define a <code>serialVersionUID</code> field.&nbsp;
  A change as simple as adding a reference to a .class object
    will add synthetic fields to the class,
   which will unfortunately change the implicit
   serialVersionUID (e.g., adding a reference to <code>String.class</code>
   will generate a static field <code>class$java$lang$String</code>).
   Also, different source code to bytecode compilers may use different
   naming conventions for synthetic variables generated for
   references to class objects or inner classes.
   To ensure interoperability of Serializable across versions,
   consider adding an explicit serialVersionUID.</h5>

--------



## 71.


*  Bad practice - Non-serializable value stored into instance field of a serializable class

system_tags : null, priority : 3; plugin_rule_key : SE_BAD_FIELD_STORE

<h5> A non-serializable value is stored into a non-transient field
of a serializable class.</h5>

--------



## 72.


*  Bad practice - Class is Externalizable but doesn't define a void constructor

system_tags : null, priority : 2; plugin_rule_key : SE_NO_SUITABLE_CONSTRUCTOR_FOR_EXTERNALIZATION

<h5> This class implements the <code>Externalizable</code> interface, but does
  not define a void constructor. When Externalizable objects are deserialized,
   they first need to be constructed by invoking the void
   constructor. Since this class does not have one,
   serialization and deserialization will fail at runtime.</h5>

--------



## 73.


*  Correctness - Using pointer equality to compare different types

system_tags : null, priority : 3; plugin_rule_key : EC_UNRELATED_TYPES_USING_POINTER_EQUALITY

<h5> This method uses using pointer equality to compare two references that seem to be of
different types.  The result of this comparison will always be false at runtime.
</h5>

--------



## 74.


*  Multithreaded correctness - Invokes run on a thread (did you mean to start it instead?)

system_tags : null, priority : 2; plugin_rule_key : RU_INVOKE_RUN

<h5> This method explicitly invokes <code>run()</code> on an object.&nbsp;
  In general, classes implement the <code>Runnable</code> interface because
  they are going to have their <code>run()</code> method invoked in a new thread,
  in which case <code>Thread.start()</code> is the right method to call.</h5>

<p>
This rule is deprecated, use {rule:squid:S1217} instead.
</p>

--------



## 75.


*  Unused public or protected field

system_tags : null, priority : 0; plugin_rule_key : UUF_UNUSED_PUBLIC_OR_PROTECTED_FIELD

<h5>This field is never used.  The field is public or protected, so perhaps it is intended to be used 
with classes not seen as part of the analysis. If not, consider removing it from the class.</h5>

--------



## 76.


*  Correctness - Method attempts to access a result set field with index 0

system_tags : null, priority : 3; plugin_rule_key : SQL_BAD_RESULTSET_ACCESS

<h5> A call to getXXX or updateXXX methods of a result set was made where the
field index is 0. As ResultSet fields start at index 1, this is always a mistake.</h5>

--------



## 77.


*  Performance - Primitive value is boxed and then immediately unboxed

system_tags : null, priority : 2; plugin_rule_key : BX_BOXING_IMMEDIATELY_UNBOXED

<h5>A primitive is boxed, and then immediately unboxed. This probably is due to a manual
	boxing in a place where an unboxed value is required, thus forcing the compiler
to immediately undo the work of the boxing.
</h5>

--------



## 78.


*  Correctness - JUnit assertion in run method will not be noticed by JUnit

system_tags : null, priority : 3; plugin_rule_key : IJU_ASSERT_METHOD_INVOKED_FROM_RUN_METHOD

<h5> A JUnit assertion is performed in a run method. Failed JUnit assertions
just result in exceptions being thrown.
Thus, if this exception occurs in a thread other than the thread that invokes
the test method, the exception will terminate the thread but not result
in the test failing.
</h5>

--------



## 79.


*  Correctness - Array formatted in useless way using format string

system_tags : null, priority : 2; plugin_rule_key : VA_FORMAT_STRING_BAD_CONVERSION_FROM_ARRAY

<h5>
One of the arguments being formatted with a format string is an array. This will be formatted
using a fairly useless format, such as [I@304282, which doesn't actually show the contents
of the array.
Consider wrapping the array using <code>Arrays.asList(...)</code> before handling it off to a formatted.
</h5>

--------



## 80.


*  Bad practice - Usage of GetResource may be unsafe if class is extended

system_tags : null, priority : 2; plugin_rule_key : UI_INHERITANCE_UNSAFE_GETRESOURCE

<h5>Calling <code>this.getClass().getResource(...)</code> could give
results other than expected if this class is extended by a class in
another package.</h5>

--------



## 81.


*  Bad practice - Static initializer creates instance before all static final fields assigned

system_tags : null, priority : 3; plugin_rule_key : SI_INSTANCE_BEFORE_FINALS_ASSIGNED

<h5> The class's static initializer creates an instance of the class
before all of the static final fields are assigned.</h5>

--------



## 82.


*  Correctness - Repeated conditional tests

system_tags : null, priority : 2; plugin_rule_key : RpC_REPEATED_CONDITIONAL_TEST

<h5>The code contains a conditional test is performed twice, one right after the other
(e.g., <code>x == 0 || x == 0</code>). Perhaps the second occurrence is intended to be something else
(e.g., <code>x == 0 || y == 0</code>). 
</h5>

--------



## 83.


*  Multithreaded correctness - Synchronize and null check on the same field.

system_tags : null, priority : 2; plugin_rule_key : NP_SYNC_AND_NULL_CHECK_FIELD

<h5>Since the field is synchronized on, it seems not likely to be null.
If it is null and then synchronized on a NullPointerException will be
thrown and the check would be pointless. Better to synchronize on 
another field.</h5>

--------



## 84.


*  Correctness - Useless assignment in return statement

system_tags : null, priority : 3; plugin_rule_key : DLS_DEAD_LOCAL_STORE_IN_RETURN

<h5>
This statement assigns to a local variable in a return statement. This assignment 
has effect. Please verify that this statement does the right thing.
</h5>

--------



## 85.


*  Bad practice - Class inherits equals() and uses Object.hashCode()

system_tags : null, priority : 3; plugin_rule_key : HE_INHERITS_EQUALS_USE_HASHCODE

<h5> This class inherits <code>equals(Object)</code> from an abstract
  superclass, and <code>hashCode()</code> from
<code>java.lang.Object</code> (which returns
  the identity hash code, an arbitrary value assigned to the object
  by the VM).&nbsp; Therefore, the class is very likely to violate the
  invariant that equal objects must have equal hashcodes.</h5>

  <p>If you don't want to define a hashCode method, and/or don't
   believe the object will ever be put into a HashMap/Hashtable,
   define the <code>hashCode()</code> method
   to throw <code>UnsupportedOperationException</code>.</p>

--------



## 86.


*  Correctness - File.separator used for regular expression

system_tags : null, priority : 3; plugin_rule_key : RE_CANT_USE_FILE_SEPARATOR_AS_REGULAR_EXPRESSION

<h5>
The code here uses <code>File.separator</code> 
where a regular expression is required. This will fail on Windows
platforms, where the <code>File.separator</code> is a backslash, which is interpreted in a
regular expression as an escape character. Amoung other options, you can just use
<code>File.separatorChar=='\\' &amp; "\\\\" : File.separator</code> instead of
<code>File.separator</code>

</h5>

--------



## 87.


*  Multithreaded correctness - Wait not in loop

system_tags : null, priority : 3; plugin_rule_key : WA_NOT_IN_LOOP

<h5> This method contains a call to <code>java.lang.Object.wait()</code>
  which is not in a loop.&nbsp; If the monitor is used for multiple conditions,
  the condition the caller intended to wait for might not be the one
  that actually occurred.</h5>

--------



## 88.


*  Bad practice - Method may fail to close stream on exception

system_tags : null, priority : 3; plugin_rule_key : OS_OPEN_STREAM_EXCEPTION_PATH

<h5> The method creates an IO stream object, does not assign it to any
fields, pass it to other methods, or return it, and does not appear to close
it on all possible exception paths out of the method.&nbsp;
This may result in a file descriptor leak.&nbsp; It is generally a good
idea to use a <code>finally</code> block to ensure that streams are
closed.</h5>

--------



## 89.


*  Correctness - Can't use reflection to check for presence of annotation without runtime retention

system_tags : null, priority : 2; plugin_rule_key : DMI_ANNOTATION_IS_NOT_VISIBLE_TO_REFLECTION

<h5> Unless an annotation has itself been annotated with  @Retention(RetentionPolicy.RUNTIME), the annotation can't be observed using reflection
(e.g., by using the isAnnotationPresent method).
   .</h5>

--------



## 90.


*  Method relaxes nullness annotation on return value

system_tags : null, priority : 2; plugin_rule_key : NP_METHOD_RETURN_RELAXING_ANNOTATION

<h5>
A method should always implement the contract of a method it overrides. Thus, if a method takes is annotated
as returning a @Nonnull value,
you shouldn't override that method in a subclass with a method annotated as returning a @Nullable or @CheckForNull value.
Doing so violates the contract that the method shouldn't return null.
</h5>

--------



## 91.


*  Correctness - Null pointer dereference

system_tags : null, priority : 3; plugin_rule_key : NP_ALWAYS_NULL

<h5> A null pointer is dereferenced here.&nbsp; This will lead to a
<code>NullPointerException</code> when the code is executed.</h5>

--------



## 92.


*  Multithreaded correctness - Static Calendar

system_tags : null, priority : 3; plugin_rule_key : STCAL_STATIC_CALENDAR_INSTANCE

<h5>Even though the JavaDoc does not contain a hint about it, Calendars are inherently unsafe for multihtreaded use. 
Sharing a single instance across thread boundaries without proper synchronization will result in erratic behavior of the
application. Under 1.4 problems seem to surface less often than under Java 5 where you will probably see
random ArrayIndexOutOfBoundsExceptions or IndexOutOfBoundsExceptions in sun.util.calendar.BaseCalendar.getCalendarDateFromFixedDate().</h5>
<p>You may also experience serialization problems.</p>
<p>Using an instance field is recommended.</p>
<p>For more information on this see <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6231579">Sun Bug #6231579</a>
and <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6178997">Sun Bug #6178997</a>.</p>

--------



## 93.


*  Performance - Unused field

system_tags : null, priority : 2; plugin_rule_key : UUF_UNUSED_FIELD

<h5> This field is never used.&nbsp; Consider removing it from the class.</h5>

--------



## 94.


*  Correctness - Value is null and guaranteed to be dereferenced on exception path

system_tags : null, priority : 3; plugin_rule_key : NP_GUARANTEED_DEREF_ON_EXCEPTION_PATH

<h5>
			  There is a statement or branch on an exception path
				that if executed guarantees that
			  a value is null at this point, and that 
			  value that is guaranteed to be dereferenced
			  (except on forward paths involving runtime exceptions).
			  </h5>

--------



## 95.


*  Multithreaded correctness - Field not guarded against concurrent access

system_tags : null, priority : 3; plugin_rule_key : IS_FIELD_NOT_GUARDED

<h5> This field is annotated with net.jcip.annotations.GuardedBy, 
but can be accessed in a way that seems to violate the annotation.</h5>

--------



## 96.


*  Bad practice - Class defines equals() but not hashCode()

system_tags : null, priority : 2; plugin_rule_key : HE_EQUALS_NO_HASHCODE

<h5> This class overrides <code>equals(Object)</code>, but does not
  override <code>hashCode()</code>.&nbsp; Therefore, the class may violate the
  invariant that equal objects must have equal hashcodes.</h5>

<p>
This rule is deprecated, use {rule:squid:S1206} instead.
</p>

--------



## 97.


*  Bad practice - Clone method may return null

system_tags : null, priority : 3; plugin_rule_key : NP_CLONE_COULD_RETURN_NULL

<h5>
	This clone method seems to return null in some circumstances, but clone is never
	allowed to return a null value.  If you are convinced this path is unreachable, throw an AssertionError
	instead.
      </h5>

--------



## 98.


*  Correctness - Bad comparison of signed byte

system_tags : null, priority : 3; plugin_rule_key : INT_BAD_COMPARISON_WITH_SIGNED_BYTE

<h5> Signed bytes can only have a value in the range -128 to 127. Comparing
a signed byte with a value outside that range is vacuous and likely to be incorrect.
To convert a signed byte <code>b</code> to an unsigned value in the range 0..255,
use <code>0xff &amp; b</code>
</h5>

--------



## 99.


*  Correctness - Method doesn't override method in superclass due to wrong package for parameter

system_tags : null, priority : 2; plugin_rule_key : NM_WRONG_PACKAGE

<h5> The method in the subclass doesn't override a similar method in a superclass because the type of a parameter doesn't exactly match
the type of the corresponding parameter in the superclass. For example, if you have:</h5>

<blockquote>
<pre>
import alpha.Foo;
public class A {
  public int f(Foo x) { return 17; }
}
----
import beta.Foo;
public class B extends A {
  public int f(Foo x) { return 42; }
}
</pre>
</blockquote>

<p>The <code>f(Foo)</code> method defined in class <code>B</code> doesn't
override the 
<code>f(Foo)</code> method defined in class <code>A</code>, because the argument
types are <code>Foo</code>'s from different packages.
</p>

--------



## 100.


*  Dodgy - Useless control flow

system_tags : null, priority : 3; plugin_rule_key : UCF_USELESS_CONTROL_FLOW

<h5> This method contains a useless control flow statement, where
control flow continues onto the same place regardless of whether or not
the branch is taken. For example,
this is caused by having an empty statement
block for an <code>if</code> statement:</h5>
<pre>
    if (argv.length == 0) {
	// TODO: handle this case
	}
</pre>

--------



## 101.


*  Correctness - Don't use removeAll to clear a collection

system_tags : null, priority : 3; plugin_rule_key : DMI_USING_REMOVEALL_TO_CLEAR_COLLECTION

<h5> If you want to remove all elements from a collection <code>c</code>, use <code>c.clear</code>,
not <code>c.removeAll(c)</code>.
	</h5>

--------



## 102.


*  Bad practice - equals() method does not check for null argument

system_tags : null, priority : 3; plugin_rule_key : NP_EQUALS_SHOULD_HANDLE_NULL_ARGUMENT

<h5>
      This implementation of equals(Object) violates the contract defined
      by java.lang.Object.equals() because it does not check for null
      being passed as the argument.  All equals() methods should return
      false if passed a null value.
      </h5>

--------



## 103.


*  Security - A prepared statement is generated from a nonconstant String

system_tags : null, priority : 3; plugin_rule_key : SQL_PREPARED_STATEMENT_GENERATED_FROM_NONCONSTANT_STRING

<h5>The code creates an SQL prepared statement from a nonconstant String.
If unchecked, tainted data from a user is used in building this String, SQL injection could
be used to make the prepared statement do something unexpected and undesirable.
</h5>

--------



## 104.


*  Correctness - Integer shift by an amount not in the range 0..31

system_tags : null, priority : 3; plugin_rule_key : ICAST_BAD_SHIFT_AMOUNT

<h5>
The code performs an integer shift by a constant amount outside
the range 0..31.
The effect of this is to use the lower 5 bits of the integer
value to decide how much to shift by. This probably isn't want was expected,
and it at least confusing.
</h5>

--------



## 105.


*  Dodgy - int division result cast to double or float

system_tags : null, priority : 3; plugin_rule_key : ICAST_IDIV_CAST_TO_DOUBLE

<h5>
This code casts the result of an integer division operation to double or 
float.
Doing division on integers truncates the result
to the integer value closest to zero.  The fact that the result
was cast to double suggests that this precision should have been retained.
What was probably meant was to cast one or both of the operands to
double <em>before</em> performing the division.  Here is an example:
</h5>
<blockquote>
<pre>
int x = 2;
int y = 5;
// Wrong: yields result 0.0
double value1 =  x / y;

// Right: yields result 0.4
double value2 =  x / (double) y;
</pre>
</blockquote>

--------



## 106.


*  Bad practice - The readResolve method must be declared with a return type of Object.

system_tags : null, priority : 2; plugin_rule_key : SE_READ_RESOLVE_MUST_RETURN_OBJECT

<h5> In order for the readResolve method to be recognized by the serialization
mechanism, it must be declared to have a return type of Object.
</h5>

--------



## 107.


*  Correctness - Class overrides a method implemented in super class Adapter wrongly

system_tags : null, priority : 3; plugin_rule_key : BOA_BADLY_OVERRIDDEN_ADAPTER

<h5> This method overrides a method found in a parent class, where that class is an Adapter that implements
a listener defined in the java.awt.event or javax.swing.event package. As a result, this method will not
get called when the event occurs.</h5>

--------



## 108.


*  Correctness - Unnecessary type check done using instanceof operator

system_tags : null, priority : 3; plugin_rule_key : SIO_SUPERFLUOUS_INSTANCEOF

<h5> Type check performed using the instanceof operator where it can be statically determined whether the object
is of the type requested. </h5>

--------



## 109.


*  Experimental - Method superfluously delegates to parent class method

system_tags : null, priority : 0; plugin_rule_key : USM_USELESS_SUBCLASS_METHOD

<h5>
      This derived method merely calls the same superclass method passing in the exact parameters
      received. This method can be removed, as it provides no additional value.
      </h5>

--------



## 110.


*  Performance - Inefficient use of keySet iterator instead of entrySet iterator

system_tags : null, priority : 3; plugin_rule_key : WMI_WRONG_MAP_ITERATOR

<h5> This method accesses the value of a Map entry, using a key that was retrieved from
a keySet iterator. It is more efficient to use an iterator on the entrySet of the map, to avoid the
Map.get(key) lookup.</h5>

--------



## 111.


*  Correctness - Useless control flow to next line

system_tags : null, priority : 3; plugin_rule_key : UCF_USELESS_CONTROL_FLOW_NEXT_LINE

<h5> This method contains a useless control flow statement in which control
flow follows to the same or following line regardless of whether or not
the branch is taken.
Often, this is caused by inadvertently using an empty statement as the
body of an <code>if</code> statement, e.g.:</h5>
<pre>
    if (argv.length == 1);
        System.out.println("Hello, " + argv[0]);
</pre>

--------



## 112.


*  Malicious code vulnerability - May expose internal static state by storing a mutable object into a static field

system_tags : null, priority : 2; plugin_rule_key : EI_EXPOSE_STATIC_REP2

<h5> This code stores a reference to an externally mutable object into a static
   field.
   If unchecked changes to
   the mutable object would compromise security or other
   important properties, you will need to do something different.
  Storing a copy of the object is better approach in many situations.</h5>

--------



## 113.


*  Correctness - Null value is guaranteed to be dereferenced

system_tags : null, priority : 4; plugin_rule_key : NP_GUARANTEED_DEREF

<h5>
			  There is a statement or branch that if executed guarantees that
			  a value is null at this point, and that 
			  value that is guaranteed to be dereferenced
			  (except on forward paths involving runtime exceptions).
			  </h5>

--------



## 114.


*  Multithreaded correctness - Condition.await() not in loop

system_tags : null, priority : 3; plugin_rule_key : WA_AWAIT_NOT_IN_LOOP

<h5> This method contains a call to <code>java.util.concurrent.await()</code>
   (or variants)
  which is not in a loop.&nbsp; If the object is used for multiple conditions,
  the condition the caller intended to wait for might not be the one
  that actually occurred.</h5>

--------



## 115.


*  Bad practice - Use of member identifier that is a keyword in later versions of Java

system_tags : null, priority : 2; plugin_rule_key : NM_FUTURE_KEYWORD_USED_AS_MEMBER_IDENTIFIER

<h5>This identifier is used as a keyword in later versions of Java. This code, and 
any code that references this API, 
will need to be changed in order to compile it in later versions of Java.</h5>

--------



## 116.


*  Multithreaded correctness - Constructor invokes Thread.start()

system_tags : null, priority : 3; plugin_rule_key : SC_START_IN_CTOR

<h5> The constructor starts a thread. This is likely to be wrong if
   the class is ever extended/subclassed, since the thread will be started
   before the subclass constructor is started.</h5>

--------



## 117.


*  Dodgy - Consider returning a zero length array rather than null

system_tags : null, priority : 2; plugin_rule_key : PZLA_PREFER_ZERO_LENGTH_ARRAYS

<h5> It is often a better design to
return a length zero array rather than a null reference to indicate that there
are no results (i.e., an empty list of results).
This way, no explicit check for null is needed by clients of the method.</h5>

<p>On the other hand, using null to indicate
"there is no answer to this question" is probably appropriate.
For example, <code>File.listFiles()</code> returns an empty list
if given a directory containing no files, and returns null if the file
is not a directory.</p>

<p>
This rule is deprecated, use {rule:squid:S1168} instead.
</p>

--------



## 118.


*  Correctness - Invocation of hashCode on an array

system_tags : null, priority : 3; plugin_rule_key : DMI_INVOKING_HASHCODE_ON_ARRAY

<h5>
The code invokes hashCode on an array. Calling hashCode on
an array returns the same value as System.identityHashCode, and ingores
the contents and length of the array. If you need a hashCode that
depends on the contents of an array <code>a</code>, 
use <code>java.util.Arrays.hashCode(a)</code>.

</h5>

--------



## 119.


*  Correctness - Uninitialized read of field method called from constructor of superclass

system_tags : null, priority : 2; plugin_rule_key : UR_UNINIT_READ_CALLED_FROM_SUPER_CONSTRUCTOR

<h5>This method is invoked in the constructor of of the superclass. At this point, the fields of the class have not yet initialized. To make this more concrete, consider the following classes:</h5>
<pre>
  abstract class A {
    int hashCode;
    abstract Object getValue();
    A() {
      hashCode = getValue().hashCode();
    }
  }
  class B extends A {
    Object value;
    B(Object v) {
      this.value = v;
    }
    Object getValue() {
      return value;
    }
  }
</pre>
<p>When a B is constructed, the constructor for the A class is invoked before the constructor for B sets value. Thus, when the constructor for A invokes getValue, an uninitialized value is read for value.</p>

--------



## 120.


*  Correctness - Nonsensical self computation involving a variable (e.g., x & x)

system_tags : null, priority : 3; plugin_rule_key : SA_LOCAL_SELF_COMPUTATION

<h5> This method performs a nonsensical computation of a local variable with another
reference to the same variable (e.g., x&x or x-x). Because of the nature
of the computation, this operation doesn't seem to make sense,
and may indicate a typo or
a logic error.  Double check the computation.
</h5>

--------



## 121.


*  Correctness - Illegal format string

system_tags : null, priority : 3; plugin_rule_key : VA_FORMAT_STRING_ILLEGAL

<h5>
The format string is syntactically invalid, 
and a runtime exception will occur when 
this statement is executed.
</h5>

--------



## 122.


*  Correctness - Method call passes null for nonnull parameter (ALL_TARGETS_DANGEROUS)

system_tags : null, priority : 3; plugin_rule_key : NP_NULL_PARAM_DEREF_ALL_TARGETS_DANGEROUS

<h5>
      A possibly-null value is passed at a call site where all known
      target methods require the parameter to be nonnull.
	Either the parameter is annotated as a parameter that should
	always be nonnull, or analysis has shown that it will always be 
	dereferenced.
      </h5>

--------



## 123.


*  Experimental - Missing expected or desired warning from FindBugs

system_tags : null, priority : 0; plugin_rule_key : FB_MISSING_EXPECTED_WARNING

<h5>
      FindBugs didn't generate generated a warning that, according to a @ExpectedWarning annotated,
      is expected or desired
      </h5>

--------



## 124.


*  Correctness - The readResolve method must not be declared as a static method.

system_tags : null, priority : 2; plugin_rule_key : SE_READ_RESOLVE_IS_STATIC

<h5> In order for the readResolve method to be recognized by the serialization
mechanism, it must not be declared as a static method.
</h5>

--------



## 125.


*  Dodgy - Class implements same interface as superclass

system_tags : null, priority : 2; plugin_rule_key : RI_REDUNDANT_INTERFACES

<h5>
    This class declares that it implements an interface that is also implemented by a superclass.
    This is redundant because once a superclass implements an interface, all subclasses by default also
    implement this interface. It may point out that the inheritance hierarchy has changed since
    this class was created, and consideration should be given to the ownership of
    the interface's implementation.
    </h5>

--------



## 126.


*  Dodgy - Class extends Servlet class and uses instance variables

system_tags : null, priority : 3; plugin_rule_key : MTIA_SUSPECT_SERVLET_INSTANCE_FIELD

<h5>
    This class extends from a Servlet class, and uses an instance member variable. Since only
    one instance of a Servlet class is created by the J2EE framework, and used in a
    multithreaded way, this paradigm is highly discouraged and most likely problematic. Consider
    only using method local variables.
    </h5>

--------



## 127.


*  Bad practice - Finalizer only nulls fields

system_tags : null, priority : 2; plugin_rule_key : FI_FINALIZER_ONLY_NULLS_FIELDS

<h5> This finalizer does nothing except null out fields. This is completely pointless, and requires that
the object be garbage collected, finalized, and then garbage collected again. You should just remove the finalize
method.

--------



## 128.


*  Correctness - No previous argument for format string

system_tags : null, priority : 3; plugin_rule_key : VA_FORMAT_STRING_NO_PREVIOUS_ARGUMENT

<h5>
The format string specifies a relative index to request that the argument for the previous format specifier
be reused. However, there is no previous argument.
For example, 
</h5>
<p><code>formatter.format("%&lt;s %s", "a", "b")</code>
</p>
<p>would throw a MissingFormatArgumentException when executed.
</p>

--------



## 129.


*  Experimental - Method may fail to clean up stream or resource

system_tags : null, priority : 0; plugin_rule_key : OBL_UNSATISFIED_OBLIGATION

<h5>
      This method may fail to clean up (close, dispose of) a stream,
      database object, or other
      resource requiring an explicit cleanup operation.
      </h5>
      <p>
      In general, if a method opens a stream or other resource,
      the method should use a try/finally block to ensure that
      the stream or resource is cleaned up before the method
      returns.
      </p>
      <p>
      This bug pattern is essentially the same as the
      OS_OPEN_STREAM and ODR_OPEN_DATABASE_RESOURCE
      bug patterns, but is based on a different
      (and hopefully better) static analysis technique.
      We are interested is getting feedback about the
      usefulness of this bug pattern.
      To send feedback, either:
      </p>
      <ul>
        <li>send email to findbugs@cs.umd.edu</li>
        <li>file a bug report: <a href="http://findbugs.sourceforge.net/reportingBugs.html">http://findbugs.sourceforge.net/reportingBugs.html</a></li>
      </ul>
      <p>
      In particular,
      the false-positive suppression heuristics for this
      bug pattern have not been extensively tuned, so
      reports about false positives are helpful to us.
      </p>
      <p>
      See Weimer and Necula, <i>Finding and Preventing Run-Time Error Handling Mistakes</i>, for
      a description of the analysis technique.
      </p>

--------



## 130.


*  Experimental - Abstract Method is already defined in implemented interface

system_tags : null, priority : 0; plugin_rule_key : USM_USELESS_ABSTRACT_METHOD

<h5>
      This abstract method is already defined in an interface that is implemented by this abstract 
      class. This method can be removed, as it provides no additional value.
      </h5>

--------



## 131.


*  Dodgy - Call to unsupported method

system_tags : null, priority : 2; plugin_rule_key : DMI_UNSUPPORTED_METHOD

<h5>All targets of this method invocation throw an UnsupportedOperationException.
</h5>

--------



## 132.


*  Correctness - Random value from 0 to 1 is coerced to the integer 0

system_tags : null, priority : 2; plugin_rule_key : RV_01_TO_INT

<h5>A random value from 0 to 1 is being coerced to the integer value 0. You probably
want to multiple the random value by something else before coercing it to an integer, or use the <code>Random.nextInt(n)</code> method.
</h5>

--------



## 133.


*  Dodgy - Ambiguous invocation of either an inherited or outer method

system_tags : null, priority : 2; plugin_rule_key : IA_AMBIGUOUS_INVOCATION_OF_INHERITED_OR_OUTER_METHOD

<h5> An inner class is invoking a method that could be resolved to either a inherited method or a method defined in an outer class. By the Java semantics,
it will be resolved to invoke the inherited method, but this may not be want
you intend. If you really intend to invoke the inherited method,
invoke it by invoking the method on super (e.g., invoke super.foo(17)), and
thus it will be clear to other readers of your code and to FindBugs
that you want to invoke the inherited method, not the method in the outer class.
</h5>

--------



## 134.


*  Correctness - Check to see if ((...) & 0) == 0

system_tags : null, priority : 3; plugin_rule_key : BIT_AND_ZZ

<h5> This method compares an expression of the form (e &amp; 0) to 0,
which will always compare equal.
This may indicate a logic error or typo.</h5>

--------



## 135.


*  Performance - Method invokes inefficient new String() constructor

system_tags : null, priority : 2; plugin_rule_key : DM_STRING_VOID_CTOR

<h5> Creating a new <code>java.lang.String</code> object using the
  no-argument constructor wastes memory because the object so created will
  be functionally indistinguishable from the empty string constant
  <code>""</code>.&nbsp; Java guarantees that identical string constants
  will be represented by the same <code>String</code> object.&nbsp; Therefore,
  you should just use the empty string constant directly.</h5>

--------



## 136.


*  Multithreaded correctness - Method does not release lock on all paths

system_tags : null, priority : 3; plugin_rule_key : UL_UNRELEASED_LOCK

<h5> This method acquires a JSR-166 (<code>java.util.concurrent</code>) lock,
but does not release it on all paths out of the method.  In general, the correct idiom
for using a JSR-166 lock is:
</h5>
<pre>
    Lock l = ...;
    l.lock();
    try {
        // do something
    } finally {
        l.unlock();
    }
</pre>

--------



## 137.


*  Security - HTTP Response splitting vulnerability

system_tags : null, priority : 2; plugin_rule_key : HRS_REQUEST_PARAMETER_TO_HTTP_HEADER

<h5>This code directly writes an HTTP parameter to an HTTP header, which allows for a HTTP response splitting
vulnerability. See <a href="http://en.wikipedia.org/wiki/HTTP_response_splitting">http://en.wikipedia.org/wiki/HTTP_response_splitting</a>
for more information.</h5>
<p>FindBugs looks only for the most blatant, obvious cases of HTTP response splitting.
If FindBugs found <em>any</em>, you <em>almost certainly</em> have more 
vulnerabilities that FindBugs doesn't report. If you are concerned about HTTP response splitting, you should seriously 
consider using a commercial static analysis or pen-testing tool.
</p>

--------



## 138.


*  Bad practice - Class defines clone() but doesn't implement Cloneable

system_tags : null, priority : 2; plugin_rule_key : CN_IMPLEMENTS_CLONE_BUT_NOT_CLONEABLE

<h5> This class defines a clone() method but the class doesn't implement Cloneable.
There are some situations in which this is OK (e.g., you want to control how subclasses 
can clone themselves), but just make sure that this is what you intended.
</h5>

--------



## 139.


*  Multithreaded correctness - Synchronization on interned String could lead to deadlock

system_tags : null, priority : 3; plugin_rule_key : DL_SYNCHRONIZATION_ON_SHARED_CONSTANT

<h5> The code synchronizes on interned String.
<pre>
private static String LOCK = "LOCK";
...
  synchronized(LOCK) { ...}
...
</pre>
</h5>
<p>Constant Strings are interned and shared across all other classes loaded by the JVM. Thus, this could
is locking on something that other code might also be locking. This could result in very strange and hard to diagnose
blocking and deadlock behavior. See <a href="http://www.javalobby.org/java/forums/t96352.html">http://www.javalobby.org/java/forums/t96352.html</a> and <a href="http://jira.codehaus.org/browse/JETTY-352">http://jira.codehaus.org/browse/JETTY-352</a>.
</p>

--------



## 140.


*  Correctness - Method defines a variable that obscures a field

system_tags : null, priority : 2; plugin_rule_key : MF_METHOD_MASKS_FIELD

<h5> This method defines a local variable with the same name as a field
in this class or a superclass.  This may cause the method to
read an uninitialized value from the field, leave the field uninitialized,
or both.</h5>

--------



## 141.


*  Unwritten public or protected field

system_tags : null, priority : 1; plugin_rule_key : UWF_UNWRITTEN_PUBLIC_OR_PROTECTED_FIELD

<h5>No writes were seen to this public/protected field.  All reads of it will return the default value. 
Check for errors (should it have been initialized?), or remove it if it is useless.</h5>

--------



## 142.


*  Correctness - Self comparison of field with itself

system_tags : null, priority : 3; plugin_rule_key : SA_FIELD_SELF_COMPARISON

<h5> This method compares a field with itself, and may indicate a typo or
a logic error.  Make sure that you are comparing the right things.
</h5>

--------



## 143.


*  Bad practice - Serializable inner class

system_tags : null, priority : 2; plugin_rule_key : SE_INNER_CLASS

<h5> This Serializable class is an inner class.  Any attempt to serialize
it will also serialize the associated outer instance. The outer instance is serializable,
so this won't fail, but it might serialize a lot more data than intended.
If possible, making the inner class a static inner class (also known as a nested class) should solve the 
problem.

--------



## 144.


*  Dodgy - Class is final but declares protected field

system_tags : null, priority : 1; plugin_rule_key : CI_CONFUSED_INHERITANCE

<h5>
      This class is declared to be final, but declares fields to be protected. Since the class
      is final, it can not be derived from, and the use of protected is confusing. The access
      modifier for the field should be changed to private or public to represent the true
      use for the field.
      </h5>

--------



## 145.


*  Correctness - Unwritten field

system_tags : null, priority : 1; plugin_rule_key : UWF_UNWRITTEN_FIELD

<h5>This field is never written.  All reads of it will return the default value. Check for errors (should it have been initialized?), or remove it if it is useless.</h5>

--------



## 146.


*  Bad practice - Finalizer does nothing but call superclass finalizer

system_tags : null, priority : 1; plugin_rule_key : FI_USELESS

<h5> The only thing this <code>finalize()</code> method does is call
  the superclass's <code>finalize()</code> method, making it
  redundant.&nbsp; Delete it.</h5>

--------



## 147.


*  Correctness - Apparent method/constructor confusion

system_tags : null, priority : 2; plugin_rule_key : NM_METHOD_CONSTRUCTOR_CONFUSION

<h5> This regular method has the same name as the class it is defined in. It is likely that this was intended to be a constructor.
      If it was intended to be a constructor, remove the declaration of a void return value.
	If you had accidently defined this method, realized the mistake, defined a proper constructor
	but can't get rid of this method due to backwards compatibility, deprecate the method.
</h5>

--------



## 148.


*  Multithreaded correctness - Method synchronizes on an updated field

system_tags : null, priority : 2; plugin_rule_key : ML_SYNC_ON_UPDATED_FIELD

<h5> This method synchronizes on an object
   referenced from a mutable field.
   This is unlikely to have useful semantics, since different
threads may be synchronizing on different objects.</h5>

--------



## 149.


*  Correctness - Method performs math using floating point precision

system_tags : null, priority : 3; plugin_rule_key : FL_MATH_USING_FLOAT_PRECISION

<h5>
   The method performs math operations using floating point precision.
   Floating point precision is very imprecise. For example,
   16777216.0f + 1.0f = 16777216.0f. Consider using double math instead.</h5>

--------



## 150.


*  Correctness - MessageFormat supplied where printf style format expected

system_tags : null, priority : 2; plugin_rule_key : VA_FORMAT_STRING_EXPECTED_MESSAGE_FORMAT_SUPPLIED

A method is called that expects a Java printf format string and a list of arguments. However, the format string doesn't contain any format specifiers (e.g., %s) but does contain message format elements (e.g., {0}). It is likely that the code is supplying a MessageFormat string when a printf-style format string is required. At runtime, all of the arguments will be ignored and the format string will be returned exactly as provided without any formatting.

--------



## 151.


*  Dodgy - Non serializable object written to ObjectOutput

system_tags : null, priority : 3; plugin_rule_key : DMI_NONSERIALIZABLE_OBJECT_WRITTEN

<h5>
This code seems to be passing a non-serializable object to the ObjectOutput.writeObject method.
If the object is, indeed, non-serializable, an error will result.
</h5>

--------



## 152.


*  Dodgy - Class extends Struts Action class and uses instance variables

system_tags : null, priority : 3; plugin_rule_key : MTIA_SUSPECT_STRUTS_INSTANCE_FIELD

<h5>
    This class extends from a Struts Action class, and uses an instance member variable. Since only
    one instance of a struts Action class is created by the Struts framework, and used in a
    multithreaded way, this paradigm is highly discouraged and most likely problematic. Consider
    only using method local variables. Only instance fields that are written outside of a monitor
    are reported. 
    </h5>

--------



## 153.


*  Correctness - equals() method defined that doesn't override Object.equals(Object)

system_tags : null, priority : 2; plugin_rule_key : EQ_OTHER_USE_OBJECT

<h5> This class defines an <code>equals()</code>
  method, that doesn't override the normal <code>equals(Object)</code> method
  defined in the base <code>java.lang.Object</code> class.&nbsp;
  The class should probably define a <code>boolean equals(Object)</code> method.
  </h5>

--------



## 154.


*  Useless increment in return statement

system_tags : null, priority : 2; plugin_rule_key : DLS_DEAD_LOCAL_INCREMENT_IN_RETURN

<h5>
This statement has a return such as <code>return x++;</code>.
A postfix increment/decrement does not impact the value of the expression,
so this increment/decrement has no effect.
Please verify that this statement does the right thing.
</h5>

--------



## 155.


*  Dodgy - Redundant comparison of non-null value to null

system_tags : null, priority : 3; plugin_rule_key : RCN_REDUNDANT_COMPARISON_OF_NULL_AND_NONNULL_VALUE

<h5> This method contains a reference known to be non-null with another reference
known to be null.</h5>

--------



## 156.


*  Format string should use %n rather than \n

system_tags : null, priority : 2; plugin_rule_key : VA_FORMAT_STRING_USES_NEWLINE

<h5>This format string include a newline character (\n). In format strings, it is generally preferable 
better to use %n, which will produce the platform-specific line separator.</h5>

--------



## 157.


*  Malicious code vulnerability - Field isn't final and can't be protected from malicious code

system_tags : null, priority : 2; plugin_rule_key : MS_CANNOT_BE_FINAL

<h5>
 A mutable static field could be changed by malicious code or
        by accident from another package.
   Unfortunately, the way the field is used doesn't allow
   any easy fix to this problem.</h5>

--------



## 158.


*  Correctness - Store of null value into field annotated NonNull

system_tags : null, priority : 3; plugin_rule_key : NP_STORE_INTO_NONNULL_FIELD

<h5> A value that could be null is stored into a field that has been annotated as NonNull. </h5>

--------



## 159.


*  Correctness - Invocation of toString on an anonymous array

system_tags : null, priority : 3; plugin_rule_key : DMI_INVOKING_TOSTRING_ON_ANONYMOUS_ARRAY

<h5>
The code invokes toString on an (anonymous) array.  Calling toString on an array generates a fairly useless result
such as [C@16f0472. Consider using Arrays.toString to convert the array into a readable
String that gives the contents of the array. See Programming Puzzlers, chapter 3, puzzle 12.
</h5>

--------



## 160.


*  Dodgy - Check for oddness that won't work for negative numbers

system_tags : null, priority : 3; plugin_rule_key : IM_BAD_CHECK_FOR_ODD

<h5>
The code uses x % 2 == 1 to check to see if a value is odd, but this won't work
for negative numbers (e.g., (-5) % 2 == -1). If this code is intending to check
for oddness, consider using x &amp; 1 == 1, or x % 2 != 0.
</h5>

--------



## 161.


*  Multithreaded correctness - Method spins on field

system_tags : null, priority : 2; plugin_rule_key : SP_SPIN_ON_FIELD

<h5> This method spins in a loop which reads a field.&nbsp; The compiler
  may legally hoist the read out of the loop, turning the code into an
  infinite loop.&nbsp; The class should be changed so it uses proper
  synchronization (including wait and notify calls).</h5>

--------



## 162.


*  Multithreaded correctness - Inconsistent synchronization

system_tags : null, priority : 3; plugin_rule_key : IS2_INCONSISTENT_SYNC

<h5> The fields of this class appear to be accessed inconsistently with respect
  to synchronization.&nbsp; This bug report indicates that the bug pattern detector
  judged that
  </h5>
  <ol>
  <li> The class contains a mix of locked and unlocked accesses,</li>
  <li> At least one locked access was performed by one of the class's own methods, and</li>
  <li> The number of unsynchronized field accesses (reads and writes) was no more than
       one third of all accesses, with writes being weighed twice as high as reads</li>
  </ol>

  <p> A typical bug matching this bug pattern is forgetting to synchronize
  one of the methods in a class that is intended to be thread-safe.</p>

  <p> You can select the nodes labeled "Unsynchronized access" to show the
  code locations where the detector believed that a field was accessed
  without synchronization.</p>

  <p> Note that there are various sources of inaccuracy in this detector;
  for example, the detector cannot statically detect all situations in which
  a lock is held.&nbsp; Also, even when the detector is accurate in
  distinguishing locked vs. unlocked accesses, the code in question may still
  be correct.</p>

--------



## 163.


*  Correctness - int value cast to double and then passed to Math.ceil

system_tags : null, priority : 3; plugin_rule_key : ICAST_INT_CAST_TO_DOUBLE_PASSED_TO_CEIL

<h5>
This code converts an int value to a double precision
floating point number and then
passing the result to the Math.ceil() function, which rounds a double to
the next higher integer value. This operation should always be a no-op,
since the converting an integer to a double should give a number with no fractional part.
It is likely that the operation that generated the value to be passed
to Math.ceil was intended to be performed using double precision
floating point arithmetic.
</h5>

--------



## 164.


*  Bad practice - Method may fail to close database resource on exception

system_tags : null, priority : 3; plugin_rule_key : ODR_OPEN_DATABASE_RESOURCE_EXCEPTION_PATH

<h5> The method creates a database resource (such as a database connection
or row set), does not assign it to any
fields, pass it to other methods, or return it, and does not appear to close
the object on all exception paths out of the method.&nbsp; Failure to
close database resources on all paths out of a method may
result in poor performance, and could cause the application to
have problems communicating with the database.</h5>

--------



## 165.


*  Bad practice - Class implements Cloneable but does not define or use clone method

system_tags : null, priority : 2; plugin_rule_key : CN_IDIOM

<h5>
   Class implements Cloneable but does not define or
   use the clone method.</h5>

--------



## 166.


*  Correctness - Creation of ScheduledThreadPoolExecutor with zero core threads

system_tags : null, priority : 1; plugin_rule_key : DMI_SCHEDULED_THREAD_POOL_EXECUTOR_WITH_ZERO_CORE_THREADS

<h5>(<a href="http://java.sun.com/javase/6/docs/api/java/util/concurrent/ScheduledThreadPoolExecutor.html#ScheduledThreadPoolExecutor(int)">Javadoc</a>)
A ScheduledThreadPoolExecutor with zero core threads will never execute anything; changes to the max pool size are ignored.
</h5>

--------



## 167.


*  Bad practice - Unchecked type in generic call

system_tags : null, priority : 3; plugin_rule_key : GC_UNCHECKED_TYPE_IN_GENERIC_CALL

<h5> This call to a generic collection method passes an argument
	while compile type Object where a specific type from
	the generic type parameters is expected.
	Thus, neither the standard Java type system nor static analysis
	can provide useful information on whether the
	object being passed as a parameter is of an appropriate type.
	</h5>

--------



## 168.


*  Multithreaded correctness - Synchronization on Boolean could lead to deadlock

system_tags : null, priority : 3; plugin_rule_key : DL_SYNCHRONIZATION_ON_BOOLEAN

<h5> The code synchronizes on a boxed primitive constant, such as an Boolean.
<pre>
private static Boolean inited = Boolean.FALSE;
...
  synchronized(inited) { 
    if (!inited) {
       init();
       inited = Boolean.TRUE;
       }
     }
...
</pre>
</h5>
<p>Since there normally exist only two Boolean objects, this code could be synchronizing on the same object as other, unrelated code, leading to unresponsiveness
and possible deadlock</p>

--------



## 169.


*  Bad practice - Certain swing methods needs to be invoked in Swing thread

system_tags : null, priority : 2; plugin_rule_key : SW_SWING_METHODS_INVOKED_IN_SWING_THREAD

<h5>(<a href="http://java.sun.com/developer/JDCTechTips/2003/tt1208.html#1">From JDC Tech Tip</a>): The Swing methods
show(), setVisible(), and pack() will create the associated peer for the frame.
With the creation of the peer, the system creates the event dispatch thread.
This makes things problematic because the event dispatch thread could be notifying
listeners while pack and validate are still processing. This situation could result in
two threads going through the Swing component-based GUI -- it's a serious flaw that
could result in deadlocks or other related threading issues. A pack call causes
components to be realized. As they are being realized (that is, not necessarily
visible), they could trigger listener notification on the event dispatch thread.</h5>

--------



## 170.


*  Dead store due to switch statement fall through to throw

system_tags : null, priority : 3; plugin_rule_key : SF_DEAD_STORE_DUE_TO_SWITCH_FALLTHROUGH_TO_THROW

<h5>
      A value stored in the previous switch case is ignored here due to a switch fall through to a place where an exception is thrown. 
      It is likely that you forgot to put a break or return at the end of the previous case.
      </h5>

--------



## 171.


*  Dodgy - Possible null pointer dereference due to return value of called method

system_tags : null, priority : 3; plugin_rule_key : NP_NULL_ON_SOME_PATH_FROM_RETURN_VALUE

<h5>
The return value from a method is dereferenced without a null check,
and the return value of that method is one that should generally be checked for null (which requires to use Findbugs annotations to express the developer's intend).
This may lead to a <code>NullPointerException</code> when the code is executed.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public long getTime() {
  return getDate().getTime();      // NullPointerException may occur
}

@CheckForNull                      // See javax.annotation.CheckForNull (JSR-305)
public Date getDate() { /* ... */ }
</pre>

<h2>Compliant Solution</h2>
<pre>
public long getTime() {
  Date date = getDate();
  if (date == null) {
    throw new IllegalStateException("...");
  }
  return date.getTime();
}

@CheckForNull                      // See javax.annotation.CheckForNull (JSR-305)
public Date getDate() { /* ... */ }
</pre>

--------



## 172.


*  Reliance on default encoding

system_tags : null, priority : 2; plugin_rule_key : DM_DEFAULT_ENCODING

<h5>Found a call to a method which will perform a byte to String (or String to byte) conversion, 
and will assume that the default platform encoding is suitable. This will cause the application 
behaviour to vary between platforms. Use an alternative API and specify a charset name or 
Charset object explicitly.</h5>

--------



## 173.


*  Multithreaded correctness - Possible double check of field

system_tags : null, priority : 2; plugin_rule_key : DC_DOUBLECHECK

<h5> This method may contain an instance of double-checked locking.&nbsp;
  This idiom is not correct according to the semantics of the Java memory
  model.&nbsp; For more information, see the web page
  <a href="http://www.cs.umd.edu/~pugh/java/memoryModel/DoubleCheckedLocking.html"
  >http://www.cs.umd.edu/~pugh/java/memoryModel/DoubleCheckedLocking.html</a>.</h5>

--------



## 174.


*  Correctness - Invocation of equals() on an array, which is equivalent to ==

system_tags : null, priority : 3; plugin_rule_key : EC_BAD_ARRAY_COMPARE

<h5>
This method invokes the .equals(Object o) method on an array. Since arrays do not override the equals
method of Object, calling equals on an array is the same as comparing their addresses. To compare the
contents of the arrays, use java.util.Arrays.equals(Object[], Object[]).
</h5>
<p>
  This rule is deprecated, use {rule:squid:S1294} instead.
</p>

--------



## 175.


*  Dodgy - Exception is caught when Exception is not thrown

system_tags : null, priority : 2; plugin_rule_key : REC_CATCH_EXCEPTION

<h5>
  This method uses a try-catch block that catches Exception objects, but Exception is not
  thrown within the try block, and RuntimeException is not explicitly caught.  It is a common bug pattern to
  say try { ... } catch (Exception e) { something } as a shorthand for catching a number of types of exception
  each of whose catch blocks is identical, but this construct also accidentally catches RuntimeException as well,
  masking potential bugs.
  </h5>

--------



## 176.


*  Correctness - Value annotated as never carrying a type qualifier used where value carrying that qualifier is required

system_tags : null, priority : 3; plugin_rule_key : TQ_NEVER_VALUE_USED_WHERE_ALWAYS_REQUIRED

<h5>
        A value specified as not carrying a type qualifier annotation is guaranteed
        to be consumed in a location or locations requiring that the value does
        carry that annotation.
        </h5>
        
        <p>
        More precisely, a value annotated with a type qualifier specifying when=NEVER
        is guaranteed to reach a use or uses where the same type qualifier specifies when=ALWAYS.
        </p>

        <p>
        TODO: example
        </p>

--------



## 177.


*  Correctness - Uninitialized read of field in constructor

system_tags : null, priority : 2; plugin_rule_key : UR_UNINIT_READ

<h5> This constructor reads a field which has not yet been assigned a value.&nbsp;
  This is often caused when the programmer mistakenly uses the field instead
  of one of the constructor's parameters.</h5>

--------



## 178.


*  Correctness - Vacuous call to collections

system_tags : null, priority : 3; plugin_rule_key : DMI_VACUOUS_SELF_COLLECTION_CALL

<h5> This call doesn't make sense. For any collection <code>c</code>, calling <code>c.containsAll(c)</code> should
always be true, and <code>c.retainAll(c)</code> should have no effect.
	</h5>

--------



## 179.


*  Correctness - Futile attempt to change max pool size of ScheduledThreadPoolExecutor

system_tags : null, priority : 1; plugin_rule_key : DMI_FUTILE_ATTEMPT_TO_CHANGE_MAXPOOL_SIZE_OF_SCHEDULED_THREAD_POOL_EXECUTOR

<h5>(<a href="http://java.sun.com/javase/6/docs/api/java/util/concurrent/ScheduledThreadPoolExecutor.html">Javadoc</a>)
While ScheduledThreadPoolExecutor inherits from ThreadPoolExecutor, a few of the inherited tuning methods are not useful for it. In particular, because it acts as a fixed-sized pool using corePoolSize threads and an unbounded queue, adjustments to maximumPoolSize have no useful effect.
	</h5>

--------



## 180.


*  Correctness - Incompatible bit masks (BIT_AND)

system_tags : null, priority : 3; plugin_rule_key : BIT_AND

<h5> This method compares an expression of the form (e &amp; C) to D,
which will always compare unequal
due to the specific values of constants C and D.
This may indicate a logic error or typo.</h5>

--------



## 181.


*  Correctness - Collections should not contain themselves

system_tags : null, priority : 3; plugin_rule_key : DMI_COLLECTIONS_SHOULD_NOT_CONTAIN_THEMSELVES

<h5> This call to a generic collection's method would only make sense if a collection contained 
itself (e.g., if <code>s.contains(s)</code> were true). This is unlikely to be true and would cause
problems if it were true (such as the computation of the hash code resulting in infinite recursion).
It is likely that the wrong value is being passed as a parameter.
	</h5>

--------



## 182.


*  Method may fail to clean up stream or resource on checked exception

system_tags : null, priority : 3; plugin_rule_key : OBL_UNSATISFIED_OBLIGATION_EXCEPTION_EDGE

<h5>This method may fail to clean up (close, dispose of) a stream, database object, or other resource requiring an 
explicit cleanup operation.<br/>In general, if a method opens a stream or other resource, the method should use a try/finally block to ensure 
that the stream or resource is cleaned up before the method returns.<p/>
<p>This bug pattern is essentially the same as the OS_OPEN_STREAM and ODR_OPEN_DATABASE_RESOURCE bug patterns, but is based on a different 
(and hopefully better) static analysis technique. See Weimer and Necula, Finding and Preventing Run-Time Error Handling Mistakes, for a 
description of the analysis technique. .</h5>

--------



## 183.


*  Correctness - Signature declares use of unhashable class in hashed construct

system_tags : null, priority : 3; plugin_rule_key : HE_SIGNATURE_DECLARES_HASHING_OF_UNHASHABLE_CLASS

<h5> A method, field or class declares a generic signature where a non-hashable class
is used in context where a hashable class is required.
A class that declares an equals method but inherits a hashCode() method
from Object is unhashable, since it doesn't fulfill the requirement that
equal objects have equal hashCodes.
</h5>

--------



## 184.


*  Correctness - Call to equals() with null argument

system_tags : null, priority : 3; plugin_rule_key : EC_NULL_ARG

<h5> This method calls equals(Object), passing a null value as
the argument. According to the contract of the equals() method,
this call should always return <code>false</code>.</h5>

--------



## 185.


*  Value without a type qualifier used where a value is required to have that qualifier

system_tags : null, priority : 2; plugin_rule_key : TQ_UNKNOWN_VALUE_USED_WHERE_ALWAYS_STRICTLY_REQUIRED

<h5>
A value is being used in a way that requires the value be annotation with a type qualifier. The type qualifier is strict, so the tool rejects any values that do not have the appropriate annotation.
</h5>
<p>
To coerce a value to have a strict annotation, define an identity function where the return value is annotated with the strict annotation. This is the only way to turn a non-annotated value into a value with a strict type qualifier annotation.
</p>

--------



## 186.


*  Correctness - Method may return null, but is declared @NonNull

system_tags : null, priority : 3; plugin_rule_key : NP_NONNULL_RETURN_VIOLATION

<h5>
      This method may return a null value, but the method (or a superclass method
      which it overrides) is declared to return @NonNull.
      </h5>

--------



## 187.


*  Correctness - Primitive array passed to function expecting a variable number of object arguments

system_tags : null, priority : 3; plugin_rule_key : VA_PRIMITIVE_ARRAY_PASSED_TO_OBJECT_VARARG

<h5>
This code passes a primitive array to a function that takes a variable number of object arguments.
This creates an array of length one to hold the primitive array and passes it to the function.
</h5>

--------



## 188.


*  Dodgy - Dead store to local variable

system_tags : null, priority : 3; plugin_rule_key : DLS_DEAD_LOCAL_STORE

<h5>
This instruction assigns a value to a local variable,
but the value is not read or used in any subsequent instruction.
Often, this indicates an error, because the value computed is never
used.
</h5>
<p>
Note that Sun's javac compiler often generates dead stores for
final local variables.  Because FindBugs is a bytecode-based tool,
there is no easy way to eliminate these false positives.
</p>

--------



## 189.


*  Bad practice - Class defines equals() and uses Object.hashCode()

system_tags : null, priority : 3; plugin_rule_key : HE_EQUALS_USE_HASHCODE

<h5> This class overrides <code>equals(Object)</code>, but does not
  override <code>hashCode()</code>, and inherits the implementation of
  <code>hashCode()</code> from <code>java.lang.Object</code> (which returns
  the identity hash code, an arbitrary value assigned to the object
  by the VM).&nbsp; Therefore, the class is very likely to violate the
  invariant that equal objects must have equal hashcodes.</h5>

<p>If you don't think instances of this class will ever be inserted into a HashMap/HashTable,
the recommended <code>hashCode</code> implementation to use is:</p>
<pre>public int hashCode() {
  assert false : "hashCode not designed";
  return 42; // any arbitrary constant will do
  }</pre>

<p>
This rule is deprecated, use {rule:squid:S1206} instead.
</p>

--------



## 190.


*  Correctness - Bad attempt to compute absolute value of signed 32-bit random integer

system_tags : null, priority : 3; plugin_rule_key : RV_ABSOLUTE_VALUE_OF_RANDOM_INT

<h5> This code generates a random signed integer and then computes
the absolute value of that random integer.  If the number returned by the random number
generator is <code>Integer.MIN_VALUE</code>, then the result will be negative as well (since 
<code>Math.abs(Integer.MIN_VALUE) == Integer.MIN_VALUE</code>).
</h5>

--------



## 191.


*  Dodgy - Test for floating point equality

system_tags : null, priority : 3; plugin_rule_key : FE_FLOATING_POINT_EQUALITY

<h5>
    This operation compares two floating point values for equality.
    Because floating point calculations may involve rounding,
   calculated float and double values may not be accurate.
    For values that must be precise, such as monetary values,
   consider using a fixed-precision type such as BigDecimal.
    For values that need not be precise, consider comparing for equality
    within some range, for example:
    <code>if ( Math.abs(x - y) &lt; .0000001 )</code>.
   See the Java Language Specification, section 4.2.4.
    </h5>

--------



## 192.


*  Nonnull field is not initialized

system_tags : null, priority : 3; plugin_rule_key : NP_NONNULL_FIELD_NOT_INITIALIZED_IN_CONSTRUCTOR

<h5>
The field is marked as nonnull, but isn't written to by the constructor.
The field might be initialized elsewhere during constructor, or might always
be initialized before use.
</h5>

--------



## 193.


*  Bad practice - Class names shouldn't shadow simple name of implemented interface

system_tags : null, priority : 2; plugin_rule_key : NM_SAME_SIMPLE_NAME_AS_INTERFACE

<h5> This class/interface has a simple name that is identical to that of an implemented/extended interface, except
that the interface is in a different package (e.g., <code>alpha.Foo</code> extends <code>beta.Foo</code>). 
This can be exceptionally confusing, create lots of situations in which you have to look at import statements
to resolve references and creates many
opportunities to accidently define methods that do not override methods in their superclasses.
</h5>

--------



## 194.


*  Multithreaded correctness - Sychronization on getClass rather than class literal

system_tags : null, priority : 3; plugin_rule_key : WL_USING_GETCLASS_RATHER_THAN_CLASS_LITERAL

<h5>
     This instance method synchronizes on <code>this.getClass()</code>. If this class is subclassed,
     subclasses will synchronize on the class object for the subclass, which isn't likely what was intended.
     For example, consider this code from java.awt.Label:
     <pre>
     private static final String base = "label";
     private static int nameCounter = 0;
     String constructComponentName() {
        synchronized (getClass()) {
            return base + nameCounter++;
        }
     }
     </pre></h5>
     <p>Subclasses of <code>Label</code> won't synchronize on the same subclass, giving rise to a datarace.
     Instead, this code should be synchronizing on <code>Label.class</code>
      <pre>
     private static final String base = "label";
     private static int nameCounter = 0;
     String constructComponentName() {
        synchronized (Label.class) {
            return base + nameCounter++;
        }
     }
     </pre></p>
      <p>Bug pattern contributed by Jason Mehrens</p>

--------



## 195.


*  Security - Nonconstant string passed to execute method on an SQL statement

system_tags : null, priority : 3; plugin_rule_key : SQL_NONCONSTANT_STRING_PASSED_TO_EXECUTE

<h5>The method invokes the execute method on an SQL statement with a String that seems
to be dynamically generated. Consider using
a prepared statement instead. It is more efficient and less vulnerable to
SQL injection attacks.
</h5>

--------



## 196.


*  Correctness - Invalid syntax for regular expression

system_tags : null, priority : 3; plugin_rule_key : RE_BAD_SYNTAX_FOR_REGULAR_EXPRESSION

<h5>
The code here uses a regular expression that is invalid according to the syntax
for regular expressions. This statement will throw a PatternSyntaxException when
executed.
</h5>

--------



## 197.


*  Dodgy - Parameter must be nonnull but is marked as nullable

system_tags : null, priority : 3; plugin_rule_key : NP_PARAMETER_MUST_BE_NONNULL_BUT_MARKED_AS_NULLABLE

<h5> This parameter is always used in a way that requires it to be nonnull,
but the parameter is explicitly annotated as being Nullable. Either the use
of the parameter or the annotation is wrong.
</h5>

--------



## 198.


*  Multithreaded correctness - Call to static Calendar

system_tags : null, priority : 3; plugin_rule_key : STCAL_INVOKE_ON_STATIC_CALENDAR_INSTANCE

<h5>Even though the JavaDoc does not contain a hint about it, Calendars are inherently unsafe for multihtreaded use. 
The detector has found a call to an instance of Calendar that has been obtained via a static
field. This looks suspicous.</h5>
<p>For more information on this see <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6231579">Sun Bug #6231579</a>
and <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6178997">Sun Bug #6178997</a>.</p>

--------



## 199.


*  BigDecimal constructed from double that isn't represented precisely

system_tags : null, priority : 2; plugin_rule_key : DMI_BIGDECIMAL_CONSTRUCTED_FROM_DOUBLE

<h5>This code creates a BigDecimal from a double value that doesn't translate well to a decimal number. For example, 
one might assume that writing <code>new BigDecimal(0.1)</code> in Java creates a BigDecimal which is exactly equal to 0.1 
(an unscaled value of 1, with a scale of 1), but it is actually equal to 0.1000000000000000055511151231257827021181583404541015625. 
You probably want to use the <code>BigDecimal.valueOf(double d)</code> method, which uses the String representation of the double to 
create the BigDecimal (e.g., <code>BigDecimal.valueOf(0.1)</code> gives 0.1).</h5>

--------



## 200.


*  Correctness - Bad comparison of nonnegative value with negative constant

system_tags : null, priority : 3; plugin_rule_key : INT_BAD_COMPARISON_WITH_NONNEGATIVE_VALUE

<h5> This code compares a value that is guaranteed to be non-negative with a negative constant.
</h5>

--------



## 201.


*  Multithreaded correctness - Inconsistent synchronization

system_tags : null, priority : 2; plugin_rule_key : IS_INCONSISTENT_SYNC

<h5> The fields of this class appear to be accessed inconsistently with respect
  to synchronization.&nbsp; This bug report indicates that the bug pattern detector
  judged that
  </h5>
  <ol>
  <li> The class contains a mix of locked and unlocked accesses,</li>
  <li> At least one locked access was performed by one of the class's own methods, and</li>
  <li> The number of unsynchronized field accesses (reads and writes) was no more than
       one third of all accesses, with writes being weighed twice as high as reads</li>
  </ol>

  <p> A typical bug matching this bug pattern is forgetting to synchronize
  one of the methods in a class that is intended to be thread-safe.</p>

  <p> Note that there are various sources of inaccuracy in this detector;
  for example, the detector cannot statically detect all situations in which
  a lock is held.&nbsp; Also, even when the detector is accurate in
  distinguishing locked vs. unlocked accesses, the code in question may still
  be correct.</p>

--------



## 202.


*  Dodgy - Remainder of hashCode could be negative

system_tags : null, priority : 3; plugin_rule_key : RV_REM_OF_HASHCODE

<h5> This code computes a hashCode, and then computes
the remainder of that value modulo another value. Since the hashCode
can be negative, the result of the remainder operation
can also be negative. </h5>
<p> Assuming you want to ensure that the result of your computation is nonnegative,
you may need to change your code.
If you know the divisor is a power of 2,
you can use a bitwise and operator instead (i.e., instead of
using <code>x.hashCode()%n</code>, use <code>x.hashCode()&amp;(n-1)</code>. 
This is probably faster than computing the remainder as well.
If you don't know that the divisor is a power of 2, take the absolute
value of the result of the remainder operation (i.e., use
<code>Math.abs(x.hashCode()%n)</code>
</p>

--------



## 203.


*  Experimental - Potential lost logger changes due to weak reference in OpenJDK

system_tags : null, priority : 0; plugin_rule_key : LG_LOST_LOGGER_DUE_TO_WEAK_REFERENCE

<h5>
      OpenJDK introduces a potential incompatibility.
      In particular, the java.util.logging.Logger behavior has
      changed. Instead of using strong references, it now uses weak references
      internally. That's a reasonable change, but unfortunately some code relies on
      the old behavior - when changing logger configuration, it simply drops the
      logger reference. That means that the garbage collector is free to reclaim
      that memory, which means that the logger configuration is lost. For example,
      consider:
      </h5>
      <p><pre>public static void initLogging() throws Exception {
      Logger logger = Logger.getLogger("edu.umd.cs");
      logger.addHandler(new FileHandler()); // call to change logger configuration
      logger.setUseParentHandlers(false); // another call to change logger configuration
      }</pre></p>
      <p>The logger reference is lost at the end of the method (it doesn't
      escape the method), so if you have a garbage collection cycle just
      after the call to initLogging, the logger configuration is lost
      (because Logger only keeps weak references).</p>
      <p><pre>public static void main(String[] args) throws Exception {
      initLogging(); // adds a file handler to the logger
      System.gc(); // logger configuration lost
      Logger.getLogger("edu.umd.cs").info("Some message"); // this isn't logged to the file as expected
      }</pre></p>
      <p><em>Ulf Ochsenfahrt and Eric Fellheimer</em>
    </p>

--------



## 204.


*  Adding elements of an entry set may fail due to reuse of Entry objects

system_tags : null, priority : 2; plugin_rule_key : DMI_ENTRY_SETS_MAY_REUSE_ENTRY_OBJECTS

<h5>The entrySet() method is allowed to return a view of the underlying Map in which a single Entry
 object is reused and returned during the iteration. As of Java 1.6, both IdentityHashMap and EnumMap
 did so. When iterating through such a Map, the Entry value is only valid until you advance to the 
 next iteration. If, for example, you try to pass such an entrySet to an addAll method, things will 
 go badly wrong.</h5>

--------



## 205.


*  Correctness - int value cast to float and then passed to Math.round

system_tags : null, priority : 3; plugin_rule_key : ICAST_INT_CAST_TO_FLOAT_PASSED_TO_ROUND

<h5>
This code converts an int value to a float precision
floating point number and then
passing the result to the Math.round() function, which returns the int/long closest
to the argument. This operation should always be a no-op,
since the converting an integer to a float should give a number with no fractional part.
It is likely that the operation that generated the value to be passed
to Math.round was intended to be performed using 
floating point arithmetic.
</h5>

--------



## 206.


*  Correctness - Bad attempt to compute absolute value of signed 32-bit hashcode

system_tags : null, priority : 3; plugin_rule_key : RV_ABSOLUTE_VALUE_OF_HASHCODE

<h5> This code generates a hashcode and then computes
the absolute value of that hashcode.  If the hashcode 
is <code>Integer.MIN_VALUE</code>, then the result will be negative as well (since 
<code>Math.abs(Integer.MIN_VALUE) == Integer.MIN_VALUE</code>).
</h5>

--------



## 207.


*  Correctness - hasNext method invokes next

system_tags : null, priority : 3; plugin_rule_key : DMI_CALLING_NEXT_FROM_HASNEXT

<h5>
The hasNext() method invokes the next() method. This is almost certainly wrong,
since the hasNext() method is not supposed to change the state of the iterator,
and the next method is supposed to change the state of the iterator.
</h5>

--------



## 208.


*  Correctness - Possible null pointer dereference

system_tags : null, priority : 3; plugin_rule_key : NP_NULL_ON_SOME_PATH

<h5> There is a branch of statement that, <em>if executed,</em>  guarantees that
a null value will be dereferenced, which
would generate a <code>NullPointerException</code> when the code is executed.
Of course, the problem might be that the branch or statement is infeasible and that
the null pointer exception can't ever be executed; deciding that is beyond the ability of FindBugs.
</h5>

--------



## 209.


*  Multithreaded correctness - Class's readObject() method is synchronized

system_tags : null, priority : 3; plugin_rule_key : RS_READOBJECT_SYNC

<h5> This serializable class defines a <code>readObject()</code> which is
  synchronized.&nbsp; By definition, an object created by deserialization
  is only reachable by one thread, and thus there is no need for
  <code>readObject()</code> to be synchronized.&nbsp; If the <code>readObject()</code>
  method itself is causing the object to become visible to another thread,
  that is an example of very dubious coding style.</h5>

--------



## 210.


*  Correctness - equals(...) used to compare incompatible arrays

system_tags : null, priority : 4; plugin_rule_key : EC_INCOMPATIBLE_ARRAY_COMPARE

This method invokes the .equals(Object o) to compare two arrays, but the arrays of of incompatible types (e.g., String[] and StringBuffer[], or String[] and int[]). They will never be equal. In addition, when equals(...) is used to compare arrays it only checks to see if they are the same array, and ignores the contents of the arrays.
<h5>
  This rule is deprecated, use {rule:squid:S1294} instead.
</h5>

--------



## 211.


*  Dodgy - Unchecked/unconfirmed cast

system_tags : null, priority : 3; plugin_rule_key : BC_UNCONFIRMED_CAST

<h5>
This cast is unchecked, and not all instances of the type casted from can be cast to
the type it is being cast to. Ensure that your program logic ensures that this
cast will not fail.
</h5>

--------



## 212.


*  Bad practice - equals method fails for subtypes

system_tags : null, priority : 3; plugin_rule_key : EQ_GETCLASS_AND_CLASS_CONSTANT

<h5> This class has an equals method that will be broken if it is inherited by subclasses.
It compares a class literal with the class of the argument (e.g., in class <code>Foo</code>
it might check if <code>Foo.class == o.getClass()</code>).
It is better to check if <code>this.getClass() == o.getClass()</code>.
</h5>

--------



## 213.


*  Correctness - Double assignment of field

system_tags : null, priority : 3; plugin_rule_key : SA_FIELD_DOUBLE_ASSIGNMENT

<h5> This method contains a double assignment of a field; e.g.
</h5>
<pre>
  int x,y;
  public void foo() {
    x = x = 17;
  }
</pre>
<p>Assigning to a field twice is useless, and may indicate a logic error or typo.</p>

--------



## 214.


*  Correctness - Number of format-string arguments does not correspond to number of placeholders

system_tags : null, priority : 3; plugin_rule_key : VA_FORMAT_STRING_ARG_MISMATCH

<h5>
A format-string method with a variable number of arguments is called,
but the number of arguments passed does not match with the number of
% placeholders in the format string.  This is probably not what the
author intended.
</h5>

--------



## 215.


*  Correctness - Primitive value is unboxed and coerced for ternary operator

system_tags : null, priority : 2; plugin_rule_key : BX_UNBOXED_AND_COERCED_FOR_TERNARY_OPERATOR

<h5>A wrapped primitive value is unboxed and converted to another primitive type as part of the
evaluation of a conditional ternary operator (the <code> b ? e1 : e2</code> operator). The
semantics of Java mandate that if <code>e1</code> and <code>e2</code> are wrapped
numeric values, the values are unboxed and converted/coerced to their common type (e.g,
if <code>e1</code> is of type <code>Integer</code> 
and <code>e2</code> is of type <code>Float</code>, then <code>e1</code> is unboxed,
converted to a floating point value, and boxed. See JLS Section 15.25.
</h5>

--------



## 216.


*  Switch statement found where one case falls through to the next case

system_tags : null, priority : 3; plugin_rule_key : SF_SWITCH_FALLTHROUGH

<h5>
      This method contains a switch statement where one case branch will fall
      through to the next case. Usually you need to end this case with a break or return.
      </h5>

<p>
This rule is deprecated, use {rule:squid:S128} instead.
</p>

--------



## 217.


*  Correctness - Double.longBitsToDouble invoked on an int

system_tags : null, priority : 3; plugin_rule_key : DMI_LONG_BITS_TO_DOUBLE_INVOKED_ON_INT

<h5> The Double.longBitsToDouble method is invoked, but a 32 bit int value is passed
	as an argument. This almostly certainly is not intended and is unlikely 
	to give the intended result.
</h5>

--------



## 218.


*  Correctness - TestCase has no tests

system_tags : null, priority : 3; plugin_rule_key : IJU_NO_TESTS

<h5> Class is a JUnit TestCase but has not implemented any test methods</h5>

--------



## 219.


*  Correctness - "." used for regular expression

system_tags : null, priority : 3; plugin_rule_key : RE_POSSIBLE_UNINTENDED_PATTERN

<h5>
A String function is being invoked and "." is being passed
to a parameter that takes a regular expression as an argument. Is this what you intended?
For example
s.replaceAll(".", "/") will return a String in which <em>every</em>
character has been replaced by a / character.
</h5>

--------



## 220.


*  Correctness - Self comparison of value with itself

system_tags : null, priority : 3; plugin_rule_key : SA_LOCAL_SELF_COMPARISON

<h5> This method compares a local variable with itself, and may indicate a typo or
a logic error.  Make sure that you are comparing the right things.
</h5>

--------



## 221.


*  Bad practice - Superclass uses subclass during initialization

system_tags : null, priority : 2; plugin_rule_key : IC_SUPERCLASS_USES_SUBCLASS_DURING_INITIALIZATION

<h5> During the initialization of a class, the class makes an active use of a subclass.
That subclass will not yet be initialized at the time of this use.
For example, in the following code, <code>foo</code> will be null.</h5>

<pre>
public class CircularClassInitialization {
	static class InnerClassSingleton extends CircularClassInitialization {
		static InnerClassSingleton singleton = new InnerClassSingleton();
	}
	
	static CircularClassInitialization foo = InnerClassSingleton.singleton;
}
</pre>

--------



## 222.


*  Multithreaded correctness - Unsynchronized get method, synchronized set method

system_tags : null, priority : 2; plugin_rule_key : UG_SYNC_SET_UNSYNC_GET

<h5> This class contains similarly-named get and set
  methods where the set method is synchronized and the get method is not.&nbsp;
  This may result in incorrect behavior at runtime, as callers of the get
  method will not necessarily see a consistent state for the object.&nbsp;
  The get method should be made synchronized.</h5>

--------



## 223.


*  Correctness - Impossible downcast

system_tags : null, priority : 4; plugin_rule_key : BC_IMPOSSIBLE_DOWNCAST

This cast will always throw a ClassCastException. The analysis believes it knows the precise type of the value being cast, and the attempt to downcast it to a subtype will always fail by throwing a ClassCastException.

--------



## 224.


*  Correctness - Nonsensical self computation involving a field (e.g., x & x)

system_tags : null, priority : 3; plugin_rule_key : SA_FIELD_SELF_COMPUTATION

<h5> This method performs a nonsensical computation of a field with another
reference to the same field (e.g., x&x or x-x). Because of the nature
of the computation, this operation doesn't seem to make sense,
and may indicate a typo or
a logic error.  Double check the computation.
</h5>

--------



## 225.


*  Multithreaded correctness - Using notify() rather than notifyAll()

system_tags : null, priority : 3; plugin_rule_key : NO_NOTIFY_NOT_NOTIFYALL

<h5> This method calls <code>notify()</code> rather than <code>notifyAll()</code>.&nbsp;
  Java monitors are often used for multiple conditions.&nbsp; Calling <code>notify()</code>
  only wakes up one thread, meaning that the thread woken up might not be the
  one waiting for the condition that the caller just satisfied.</h5>

--------



## 226.


*  Boxed value is unboxed and then immediately reboxed

system_tags : null, priority : 2; plugin_rule_key : BX_UNBOXING_IMMEDIATELY_REBOXED

<h5>A boxed value is unboxed and then immediately reboxed.</h5>

--------



## 227.


*  Dead store due to switch statement fall through

system_tags : null, priority : 3; plugin_rule_key : SF_DEAD_STORE_DUE_TO_SWITCH_FALLTHROUGH

<h5>
      A value stored in the previous switch case is overwritten here due 
      to a switch fall through. It is likely that you forgot to put a 
      break or return at the end of the previous case.
      </h5>

--------



## 228.


*  Bad practice - Class defines compareTo(...) and uses Object.equals()

system_tags : null, priority : 3; plugin_rule_key : EQ_COMPARETO_USE_OBJECT_EQUALS

<h5> This class defines a <code>compareTo(...)</code> method but inherits its
  <code>equals()</code> method from <code>java.lang.Object</code>.
  Generally, the value of compareTo should return zero if and only if
  equals returns true. If this is violated, weird and unpredictable
  failures will occur in classes such as PriorityQueue.
  In Java 5 the PriorityQueue.remove method uses the compareTo method,
  while in Java 6 it uses the equals method.

<p>From the JavaDoc for the compareTo method in the Comparable interface:
<blockquote>
It is strongly recommended, but not strictly required that <code>(x.compareTo(y)==0) == (x.equals(y))</code>.
Generally speaking, any class that implements the Comparable interface and violates this condition
should clearly indicate this fact. The recommended language
is "Note: this class has a natural ordering that is inconsistent with equals."
</blockquote>

<p>
This rule is deprecated, use {rule:squid:S1210} instead.
</h5>

--------



## 229.


*  Multithreaded correctness - Incorrect lazy initialization and update of static field

system_tags : null, priority : 3; plugin_rule_key : LI_LAZY_INIT_UPDATE_STATIC

<h5> This method contains an unsynchronized lazy initialization of a static field.
After the field is set, the object stored into that location is further accessed. 
The setting of the field is visible to other threads as soon as it is set. If the
futher accesses in the method that set the field serve to initialize the object, then
you have a <em>very serious</em> multithreading bug, unless something else prevents
any other thread from accessing the stored object until it is fully initialized.
</h5>

--------



## 230.


*  Bad practice - serialVersionUID isn't long

system_tags : null, priority : 2; plugin_rule_key : SE_NONLONG_SERIALVERSIONID

<h5> This class defines a <code>serialVersionUID</code> field that is not long.&nbsp;
  The field should be made long
   if it is intended to specify
   the version UID for purposes of serialization.</h5>

--------



## 231.


*  Bad practice - Method may fail to close database resource

system_tags : null, priority : 3; plugin_rule_key : ODR_OPEN_DATABASE_RESOURCE

<h5> The method creates a database resource (such as a database connection
or row set), does not assign it to any
fields, pass it to other methods, or return it, and does not appear to close
the object on all paths out of the method.&nbsp; Failure to
close database resources on all paths out of a method may
result in poor performance, and could cause the application to
have problems communicating with the database.
</h5>

--------



## 232.


*  Correctness - Suspicious reference comparison to constant

system_tags : null, priority : 2; plugin_rule_key : RC_REF_COMPARISON_BAD_PRACTICE

This method compares a reference value to a constant using the == or != operator, where the correct way to compare instances of this type is generally with the equals() method. It is possible to create distinct instances that are equal but do not compare as == since they are different objects. Examples of classes which should generally not be compared by reference are java.lang.Integer, java.lang.Float, etc.

--------



## 233.


*  Class defines hashcode(); should it be hashCode()?

system_tags : null, priority : 3; plugin_rule_key : NM_LCASE_HASHCODE

<h5>
      This class defines a method called <code>hashcode()</code>.
      This method does not override the <code>hashCode()</code>
      method in <code>java.lang.Object</code>, which is probably what was intended.
      </h5>

<p>
This rule is deprecated, use {rule:squid:S1221} instead.
</p>

--------



## 234.


*  Security - JSP reflected cross site scripting vulnerability

system_tags : null, priority : 3; plugin_rule_key : XSS_REQUEST_PARAMETER_TO_JSP_WRITER

<h5>This code directly writes an HTTP parameter to JSP output, which allows for a cross site scripting
vulnerability. See <a href="http://en.wikipedia.org/wiki/Cross-site_scripting">http://en.wikipedia.org/wiki/Cross-site_scripting</a>
for more information.</h5>
<p>FindBugs looks only for the most blatant, obvious cases of cross site scripting.
If FindBugs found <em>any</em>, you <em>almost certainly</em> have more cross site scripting
vulnerabilities that FindBugs doesn't report. If you are concerned about cross site scripting, you should seriously 
consider using a commercial static analysis or pen-testing tool.
</p>

--------



## 235.


*  Performance - Method uses toArray() with zero-length array argument

system_tags : null, priority : 3; plugin_rule_key : ITA_INEFFICIENT_TO_ARRAY

<h5> This method uses the toArray() method of a collection derived class, and passes
in a zero-length prototype array argument.  It is more efficient to use
<code>myCollection.toArray(new Foo[myCollection.size()])</code>
If the array passed in is big enough to store all of the
elements of the collection, then it is populated and returned
directly. This avoids the need to create a second array
(by reflection) to return as the result.</h5>

--------



## 236.


*  Performance - Should be a static inner class

system_tags : null, priority : 2; plugin_rule_key : SIC_INNER_SHOULD_BE_STATIC

<h5> This class is an inner class, but does not use its embedded reference
  to the object which created it.&nbsp; This reference makes the instances
  of the class larger, and may keep the reference to the creator object
  alive longer than necessary.&nbsp; If possible, the class should be
   made static.
</h5>

--------



## 237.


*  Bad practice - Comparison of String parameter using == or !=

system_tags : null, priority : 2; plugin_rule_key : ES_COMPARING_PARAMETER_STRING_WITH_EQ

<h5>This code compares a <code>java.lang.String</code> parameter for reference
equality using the == or != operators. Requiring callers to 
pass only String constants or interned strings to a method is unnecessarily
fragile, and rarely leads to measurable performance gains. Consider
using the <code>equals(Object)</code> method instead.</h5>

--------



## 238.


*  Correctness - A collection is added to itself

system_tags : null, priority : 3; plugin_rule_key : IL_CONTAINER_ADDED_TO_ITSELF

<h5>A collection is added to itself. As a result, computing the hashCode of this
set will throw a StackOverflowException.
</h5>

--------



## 239.


*  Correctness - The type of a supplied argument doesn't match format specifier

system_tags : null, priority : 3; plugin_rule_key : VA_FORMAT_STRING_BAD_CONVERSION

<h5>
One of the arguments is uncompatible with the corresponding format string specifier.
As a result, this will generate a runtime exception when executed.
For example, <code>String.format("%d", "1")</code> will generate an exception, since
the String "1" is incompatible with the format specifier %d.
</h5>

--------



## 240.


*  Correctness - A parameter is dead upon entry to a method but overwritten

system_tags : null, priority : 3; plugin_rule_key : IP_PARAMETER_IS_DEAD_BUT_OVERWRITTEN

<h5>
The initial value of this parameter is ignored, and the parameter
is overwritten here. This often indicates a mistaken belief that
the write to the parameter will be conveyed back to
the caller.
</h5>

--------



## 241.


*  Bad practice - Covariant compareTo() method defined

system_tags : null, priority : 2; plugin_rule_key : CO_SELF_NO_OBJECT

<h5> This class defines a covariant version of <code>compareTo()</code>.&nbsp;
  To correctly override the <code>compareTo()</code> method in the
  <code>Comparable</code> interface, the parameter of <code>compareTo()</code>
  must have type <code>java.lang.Object</code>.</h5>

--------



## 242.


*  Malicious code vulnerability - Field is a mutable array

system_tags : null, priority : 2; plugin_rule_key : MS_MUTABLE_ARRAY

<h5> A final static field references an array
   and can be accessed by malicious code or
        by accident from another package.
   This code can freely modify the contents of the array.</h5>

--------



## 243.


*  Multithreaded correctness - Unconditional wait

system_tags : null, priority : 2; plugin_rule_key : UW_UNCOND_WAIT

<h5> This method contains a call to <code>java.lang.Object.wait()</code> which
  is not guarded by conditional control flow.&nbsp; The code should
	verify that condition it intends to wait for is not already satisfied
	before calling wait; any previous notifications will be ignored.
  </h5>

--------



## 244.


*  An increment to a volatile field isn't atomic

system_tags : null, priority : 3; plugin_rule_key : VO_VOLATILE_INCREMENT

<h5>This code increments a volatile field. Increments of volatile fields aren't atomic. If more 
than one thread is incrementing the field at the same time, increments could be lost. </h5>

--------



## 245.


*  Dead store to local variable that shadows field

system_tags : null, priority : 2; plugin_rule_key : DLS_DEAD_LOCAL_STORE_SHADOWS_FIELD

<h5>This instruction assigns a value to a local variable, but the value is not read or used in 
any subsequent instruction. Often, this indicates an error, because the value computed is never 
used. There is a field with the same name as the local variable. Did you mean to assign to that 
variable instead?</h5>

--------



## 246.


*  compareTo()/compare() returns Integer.MIN_VALUE

system_tags : null, priority : 2; plugin_rule_key : CO_COMPARETO_RESULTS_MIN_VALUE

<h5>In some situation, this compareTo or compare method returns the constant Integer.MIN_VALUE, 
which is an exceptionally bad practice. The only thing that matters about the return value of 
compareTo is the sign of the result. But people will sometimes negate the return value of compareTo, 
expecting that this will negate the sign of the result. And it will, except in the case where 
the value returned is Integer.MIN_VALUE. So just return -1 rather than Integer.MIN_VALUE.</h5>

--------



## 247.


*  Experimental - Calls to equals on a final class that doesn't override Object's equals method

system_tags : null, priority : 0; plugin_rule_key : UOE_USE_OBJECT_EQUALS

<h5>
      This method invokes the .equals(Object o) method on a final class that doesn't override the equals method
      in the Object class, effectively making the equals method test for sameness, like ==. It is good to use
      the .equals method, but you should consider adding an .equals method in this class.
      </h5>
      <p>[Bill Pugh]: Sorry, but I strongly disagree that this should be a warning, and I think your code
      is just fine. Users of your code shouldn't care how you've implemented equals(), and they should never
      depend on == to compare instances, since that bypasses the libraries ability to control how objects
      are compared.
      </p>

--------



## 248.


*  Multithreaded correctness - Synchronization on boxed primitive values

system_tags : null, priority : 3; plugin_rule_key : DL_SYNCHRONIZATION_ON_UNSHARED_BOXED_PRIMITIVE

<h5> The code synchronizes on an apparently unshared boxed primitive, 
such as an Integer.
<pre>
private static final Integer fileLock = new Integer(1);
...
  synchronized(fileLock) { 
     .. do something ..
     }
...
</pre>
</h5>
<p>It would be much better, in this code, to redeclare fileLock as
<pre>
private static final Object fileLock = new Object();
</pre>
The existing code might be OK, but it is confusing and a 
future refactoring, such as the "Remove Boxing" refactoring in IntelliJ,
might replace this with the use of an interned Integer object shared 
throughout the JVM, leading to very confusing behavior and potential deadlock.
</p>

--------



## 249.


*  Bad practice - Method with Boolean return type returns explicit null

system_tags : null, priority : 2; plugin_rule_key : NP_BOOLEAN_RETURN_NULL

<h5>
	A method that returns either Boolean.TRUE, Boolean.FALSE or null is an accident waiting to happen.
	This method can be invoked as though it returned a value of type boolean, and
	the compiler will insert automatic unboxing of the Boolean value. If a null value is returned,
	this will result in a NullPointerException.
  	 </h5>

--------



## 250.


*  Performance - Explicit garbage collection; extremely dubious except in benchmarking code

system_tags : null, priority : 2; plugin_rule_key : DM_GC

<h5> Code explicitly invokes garbage collection.
  Except for specific use in benchmarking, this is very dubious.</h5>
  <p>In the past, situations where people have explicitly invoked
  the garbage collector in routines such as close or finalize methods
  has led to huge performance black holes. Garbage collection
   can be expensive. Any situation that forces hundreds or thousands
   of garbage collections will bring the machine to a crawl.</p>

<p>
This rule is deprecated, use {rule:squid:S1215} instead.
</p>

--------



## 251.


*  Multithreaded correctness - Synchronization on boxed primitive could lead to deadlock

system_tags : null, priority : 3; plugin_rule_key : DL_SYNCHRONIZATION_ON_BOXED_PRIMITIVE

<h5> The code synchronizes on a boxed primitive constant, such as an Integer.
<pre>
private static Integer count = 0;
...
  synchronized(count) { 
     count++;
     }
...
</pre>
</h5>
<p>Since Integer objects can be cached and shared,
this code could be synchronizing on the same object as other, unrelated code, leading to unresponsiveness
and possible deadlock</p>

--------



## 252.


*  Bad practice - Method might drop exception

system_tags : null, priority : 2; plugin_rule_key : DE_MIGHT_DROP

<h5> This method might drop an exception.&nbsp; In general, exceptions
  should be handled or reported in some way, or they should be thrown
  out of the method.</h5>

--------



## 253.


*  Dodgy - Method discards result of readLine after checking if it is nonnull

system_tags : null, priority : 2; plugin_rule_key : RV_DONT_JUST_NULL_CHECK_READLINE

<h5> The value returned by readLine is discarded after checking to see if the return
value is non-null. In almost all situations, if the result is non-null, you will want
to use that non-null value. Calling readLine again will give you a different line.</h5>

--------



## 254.


*  Experimental - Bad Applet Constructor relies on uninitialized AppletStub

system_tags : null, priority : 0; plugin_rule_key : BAC_BAD_APPLET_CONSTRUCTOR

<h5>
      This constructor calls methods in the parent Applet that rely on the AppletStub. Since the AppletStub
      isn't initialized until the init() method of this applet is called, these methods will not perform
      correctly.
      </h5>

--------



## 255.


*  Performance - Unread field

system_tags : null, priority : 2; plugin_rule_key : URF_UNREAD_FIELD

<h5> This field is never read.&nbsp; Consider removing it from the class.</h5>

--------



## 256.


*  Correctness - A known null value is checked to see if it is an instance of a type

system_tags : null, priority : 4; plugin_rule_key : NP_NULL_INSTANCEOF

<h5>
This instanceof test will always return false, since the value being checked is guaranteed to be null.
Although this is safe, make sure it isn't
an indication of some misunderstanding or some other logic error.
</h5>

--------



## 257.


*  Malicious code vulnerability - Field should be package protected

system_tags : null, priority : 2; plugin_rule_key : MS_PKGPROTECT

<h5> A mutable static field could be changed by malicious code or
   by accident.
   The field could be made package protected to avoid
   this vulnerability.</h5>

--------



## 258.


*  Correctness - Value required to not have type qualifier, but marked as unknown

system_tags : null, priority : 3; plugin_rule_key : TQ_EXPLICIT_UNKNOWN_SOURCE_VALUE_REACHES_NEVER_SINK

<h5>
      A value is used in a way that requires it to be never be a value denoted by a type qualifier, but
	there is an explicit annotation stating that it is not known where the value is prohibited from having that type qualifier.
	Either the usage or the annotation is incorrect.
      </h5>

--------



## 259.


*  Experimental - Method accesses a private member variable of owning class

system_tags : null, priority : 0; plugin_rule_key : IMA_INEFFICIENT_MEMBER_ACCESS

<h5>
      This method of an inner class reads from or writes to a private member variable of the owning class,
      or calls a private method of the owning class. The compiler must generate a special method to access this
      private member, causing this to be less efficient. Relaxing the protection of the member variable or method
      will allow the compiler to treat this as a normal access.
      </h5>

--------



## 260.


*  Code checks for specific values returned by compareTo

system_tags : null, priority : 2; plugin_rule_key : RV_CHECK_COMPARETO_FOR_SPECIFIC_RETURN_VALUE

<h5>This code invoked a compareTo or compare method, and checks to see if the return value is a specific 
value, such as 1 or -1. When invoking these methods, you should only check the sign of the result, not 
for any specific non-zero value. While many or most compareTo and compare methods only return -1, 0 or 1, 
some of them will return other values.</h5>

--------



## 261.


*  int value converted to long and used as absolute time

system_tags : null, priority : 2; plugin_rule_key : ICAST_INT_2_LONG_AS_INSTANT

<h5>This code converts a 32-bit int value to a 64-bit long value, and then passes that value for a 
method parameter that requires an absolute time value. An absolute time value is the number of 
milliseconds since the standard base time known as "the epoch", namely January 1, 1970, 00:00:00 GMT. 
For example, the following method, intended to convert seconds since the epoc into a Date, is badly broken:
<pre>
Date getDate(int seconds) { return new Date(seconds * 1000); }
</pre>
</h5>
<p>The multiplication is done using 32-bit arithmetic, and then converted to a 64-bit value. When a 32-bit 
value is converted to 64-bits and used to express an absolute time value, only dates in December 1969 and 
January 1970 can be represented.</p>
<p>Correct implementations for the above method are:
<pre>
// Fails for dates after 2037
Date getDate(int seconds) { return new Date(seconds * 1000L); }

// better, works for all dates
Date getDate(long seconds) { return new Date(seconds * 1000); }
</pre>
</p>

--------



## 262.


*  Multithreaded correctness - Method calls Thread.sleep() with a lock held

system_tags : null, priority : 3; plugin_rule_key : SWL_SLEEP_WITH_LOCK_HELD

<h5>
      This method calls Thread.sleep() with a lock held.  This may result
      in very poor performance and scalability, or a deadlock, since other threads may
      be waiting to acquire the lock.  It is a much better idea to call
      wait() on the lock, which releases the lock and allows other threads
      to run.
      </h5>

--------



## 263.


*  Malicious code vulnerability - Finalizer should be protected, not public

system_tags : null, priority : 2; plugin_rule_key : FI_PUBLIC_SHOULD_BE_PROTECTED

<h5> A class's <code>finalize()</code> method should have protected access,
   not public.</h5>

--------



## 264.


*  Correctness - Unneeded use of currentThread() call, to call interrupted()

system_tags : null, priority : 3; plugin_rule_key : STI_INTERRUPTED_ON_CURRENTTHREAD

<h5>
This method invokes the Thread.currentThread() call, just to call the interrupted() method. As interrupted() is a
static method, is more simple and clear to use Thread.interrupted().
</h5>

--------



## 265.


*  Bad practice - Check for sign of bitwise operation

system_tags : null, priority : 3; plugin_rule_key : BIT_SIGNED_CHECK

<h5> This method compares an expression such as
<pre>((event.detail &amp; SWT.SELECTED) &gt; 0)</pre>.
Using bit arithmetic and then comparing with the greater than operator can
lead to unexpected results (of course depending on the value of
SWT.SELECTED). If SWT.SELECTED is a negative number, this is a candidate
for a bug. Even when SWT.SELECTED is not negative, it seems good practice
to use '!= 0' instead of '&gt; 0'.
</h5>
<p>
<em>Boris Bokowski</em>
</p>

--------



## 266.


*  Correctness - Field not initialized in constructor

system_tags : null, priority : 1; plugin_rule_key : UWF_FIELD_NOT_INITIALIZED_IN_CONSTRUCTOR

<h5>This field is never initialized within any constructor, and is therefore could be null after the object is constructed. This could be a either an error or a questionable design, since it means a null pointer exception will be generated if that field is dereferenced before being initialized.</h5>

--------



## 267.


*  Correctness - equals() method defined that doesn't override equals(Object)

system_tags : null, priority : 2; plugin_rule_key : EQ_OTHER_NO_OBJECT

<h5> This class defines an <code>equals()</code>
  method, that doesn't override the normal <code>equals(Object)</code> method
  defined in the base <code>java.lang.Object</code> class.&nbsp; Instead, it
  inherits an <code>equals(Object)</code> method from a superclass.
  The class should probably define a <code>boolean equals(Object)</code> method.
  </h5>

<p>
This rule is deprecated, use {rule:squid:S1201} instead.
</p>

--------



## 268.


*  Correctness - Method call passes null to a nonnull parameter

system_tags : null, priority : 3; plugin_rule_key : NP_NONNULL_PARAM_VIOLATION

<h5>
      This method passes a null value as the parameter of a method which
	must be nonnull. Either this parameter has been explicitly marked
	as @Nonnull, or analysis has determined that this parameter is
	always dereferenced.
      </h5>

--------



## 269.


*  Bad practice - Empty finalizer should be deleted

system_tags : null, priority : 2; plugin_rule_key : FI_EMPTY

<h5> Empty <code>finalize()</code> methods are useless, so they should
  be deleted.</h5>

--------



## 270.


*  Correctness - close() invoked on a value that is always null

system_tags : null, priority : 4; plugin_rule_key : NP_CLOSING_NULL

close() is being invoked on a value that is always null. If this statement is executed, a null pointer exception will occur. But the big risk here you never close something that should be closed.

--------



## 271.


*  Correctness - Field only ever set to null

system_tags : null, priority : 3; plugin_rule_key : UWF_NULL_FIELD

<h5> All writes to this field are of the constant value null, and thus
all reads of the field will return null.
Check for errors, or remove it if it is useless.</h5>

--------



## 272.


*  Multithreaded correctness - Naked notify

system_tags : null, priority : 3; plugin_rule_key : NN_NAKED_NOTIFY

<h5> A call to <code>notify()</code> or <code>notifyAll()</code>
  was made without any (apparent) accompanying
  modification to mutable object state.&nbsp; In general, calling a notify
  method on a monitor is done because some condition another thread is
  waiting for has become true.&nbsp; However, for the condition to be meaningful,
  it must involve a heap object that is visible to both threads.</h5>

  <p> This bug does not necessarily indicate an error, since the change to
  mutable object state may have taken place in a method which then called
  the method containing the notification.</p>

--------



## 273.


*  Bad practice - Method may fail to close stream

system_tags : null, priority : 3; plugin_rule_key : OS_OPEN_STREAM

<h5> The method creates an IO stream object, does not assign it to any
fields, pass it to other methods that might close it, 
or return it, and does not appear to close
the stream on all paths out of the method.&nbsp; This may result in
a file descriptor leak.&nbsp; It is generally a good
idea to use a <code>finally</code> block to ensure that streams are
closed.</h5>

--------



## 274.


*  Bad practice - Class names shouldn't shadow simple name of superclass

system_tags : null, priority : 2; plugin_rule_key : NM_SAME_SIMPLE_NAME_AS_SUPERCLASS

<h5> This class has a simple name that is identical to that of its superclass, except
that its superclass is in a different package (e.g., <code>alpha.Foo</code> extends <code>beta.Foo</code>). 
This can be exceptionally confusing, create lots of situations in which you have to look at import statements
to resolve references and creates many
opportunities to accidently define methods that do not override methods in their superclasses.
</h5>

--------



## 275.


*  Bad practice - Abstract class defines covariant equals() method

system_tags : null, priority : 2; plugin_rule_key : EQ_ABSTRACT_SELF

<h5> This class defines a covariant version of <code>equals()</code>.&nbsp;
  To correctly override the <code>equals()</code> method in
  <code>java.lang.Object</code>, the parameter of <code>equals()</code>
  must have type <code>java.lang.Object</code>.</h5>

<p>
This rule is deprecated, use {rule:squid:S1201} instead.
</p>

--------



## 276.


*  Bad practice - Store of non serializable object into HttpSession

system_tags : null, priority : 3; plugin_rule_key : J2EE_STORE_OF_NON_SERIALIZABLE_OBJECT_INTO_SESSION

<h5>
This code seems to be storing a non-serializable object into an HttpSession.
If this session is passivated or migrated, an error will result.
</h5>

--------



## 277.


*  Dodgy - Redundant comparison of two null values

system_tags : null, priority : 3; plugin_rule_key : RCN_REDUNDANT_COMPARISON_TWO_NULL_VALUES

<h5> This method contains a redundant comparison of two references known to
both be definitely null.</h5>

--------



## 278.


*  Performance - Could be refactored into a named static inner class

system_tags : null, priority : 2; plugin_rule_key : SIC_INNER_SHOULD_BE_STATIC_ANON

<h5> This class is an inner class, but does not use its embedded reference
  to the object which created it.&nbsp; This reference makes the instances
  of the class larger, and may keep the reference to the creator object
  alive longer than necessary.&nbsp; If possible, the class should be
  made into a <em>static</em> inner class. Since anonymous inner
classes cannot be marked as static, doing this will require refactoring
the inner class so that it is a named inner class.</h5>

--------



## 279.


*  Bad practice - Class is not derived from an Exception, even though it is named as such

system_tags : null, priority : 2; plugin_rule_key : NM_CLASS_NOT_EXCEPTION

<h5> This class is not derived from another exception, but ends with 'Exception'. This will
be confusing to users of this class.</h5>

--------



## 280.


*  Experimental - Unexpected/undesired warning from FindBugs

system_tags : null, priority : 0; plugin_rule_key : FB_UNEXPECTED_WARNING

<h5>
      FindBugs generated a warning that, according to a @NoWarning annotated,
      is unexpected or undesired
      </h5>

--------



## 281.


*  Correctness - Method must be private in order for serialization to work

system_tags : null, priority : 2; plugin_rule_key : SE_METHOD_MUST_BE_PRIVATE

<h5> This class implements the <code>Serializable</code> interface, and defines a method
  for custom serialization/deserialization. But since that method isn't declared private,
  it will be silently ignored by the serialization/deserialization API.</h5>

--------



## 282.


*  Correctness - Method assigns boolean literal in boolean expression

system_tags : null, priority : 3; plugin_rule_key : QBA_QUESTIONABLE_BOOLEAN_ASSIGNMENT

<h5>
      This method assigns a literal boolean value (true or false) to a boolean variable inside
      an if or while expression. Most probably this was supposed to be a boolean comparison using 
      ==, not an assignment using =.
      </h5>

--------



## 283.


*  Performance - Unread field: should this field be static?

system_tags : null, priority : 2; plugin_rule_key : SS_SHOULD_BE_STATIC

<h5> This class contains an instance final field that
   is initialized to a compile-time static value.
   Consider making the field static.</h5>

--------



## 284.


*  Bad practice - Explicit invocation of finalizer

system_tags : null, priority : 2; plugin_rule_key : FI_EXPLICIT_INVOCATION

<h5> This method contains an explicit invocation of the <code>finalize()</code>
  method on an object.&nbsp; Because finalizer methods are supposed to be
  executed once, and only by the VM, this is a bad idea.</h5>
<p>If a connected set of objects beings finalizable, then the VM will invoke the
finalize method on all the finalizable object, possibly at the same time in different threads.
Thus, it is a particularly bad idea, in the finalize method for a class X, invoke finalize
on objects referenced by X, because they may already be getting finalized in a separate thread.

<p>
This rule is deprecated, use {rule:squid:ObjectFinalizeCheck} instead.
</p>

--------



## 285.


*  Correctness - equals() used to compare array and nonarray

system_tags : null, priority : 3; plugin_rule_key : EC_ARRAY_AND_NONARRAY

<h5>
This method invokes the .equals(Object o) to compare an array and a reference that doesn't seem
to be an array. If things being compared are of different types, they are guaranteed to be unequal
and the comparison is almost certainly an error. Even if they are both arrays, the equals method
on arrays only determines of the two arrays are the same object.
To compare the
contents of the arrays, use java.util.Arrays.equals(Object[], Object[]).
</h5>

--------



## 286.


*  Correctness - Incompatible bit masks (BIT_IOR)

system_tags : null, priority : 3; plugin_rule_key : BIT_IOR

<h5> This method compares an expression of the form (e | C) to D.
which will always compare unequal
due to the specific values of constants C and D.
This may indicate a logic error or typo.</h5>

<p> Typically, this bug occurs because the code wants to perform
a membership test in a bit set, but uses the bitwise OR
operator ("|") instead of bitwise AND ("&amp;").</p>

--------



## 287.


*  Malicious code vulnerability - Field isn't final but should be

system_tags : null, priority : 2; plugin_rule_key : MS_SHOULD_BE_FINAL

<h5>
 A mutable static field could be changed by malicious code or
        by accident from another package.
        The field could be made final to avoid
        this vulnerability.</h5>
<p>
  This rule is deprecated, use {rule:squid:S1444} instead.
</p>

--------



## 288.


*  Bad practice - Transient field that isn't set by deserialization.

system_tags : null, priority : 2; plugin_rule_key : SE_TRANSIENT_FIELD_NOT_RESTORED

<h5> This class contains a field that is updated at multiple places in the class, thus it seems to be part of the state of the class. However, since the field is marked as transient and not set in readObject or readResolve, it will contain the default value in any 
deserialized instance of the class.
</h5>

--------



## 289.


*  Correctness - Covariant equals() method defined for enum

system_tags : null, priority : 2; plugin_rule_key : EQ_DONT_DEFINE_EQUALS_FOR_ENUM

<h5> This class defines an enumeration, and equality on enumerations are defined
using object identity. Defining a covariant equals method for an enumeration
value is exceptionally bad practice, since it would likely result
in having two different enumeration values that compare as equals using
the covariant enum method, and as not equal when compared normally.
Don't do it.
</h5>

<p>
This rule is deprecated, use {rule:squid:S1201} instead.
</p>

--------



## 290.


*  Correctness - More arguments are passed that are actually used in the format string

system_tags : null, priority : 2; plugin_rule_key : VA_FORMAT_STRING_EXTRA_ARGUMENTS_PASSED

<h5>
A format-string method with a variable number of arguments is called,
but more arguments are passed than are actually used by the format string.
This won't cause a runtime exception, but the code may be silently omitting 
information that was intended to be included in the formatted string.
</h5>

--------



## 291.


*  Correctness - equals method always returns false

system_tags : null, priority : 4; plugin_rule_key : EQ_ALWAYS_FALSE

<h5> This class defines an equals method that always returns false. This means that an object is not equal to itself, and it is impossible to create useful Maps or Sets of this class. More fundamentally, it means
that equals is not reflexive, one of the requirements of the equals method.</h5>
<p>The likely intended semantics are object identity: that an object is equal to itself. This is the behavior inherited from class <code>Object</code>. If you need to override an equals inherited from a different 
superclass, you can use use:
<pre>
public boolean equals(Object o) { return this == o; }
</pre>
</p>

--------



## 292.


*  Unread public/protected field

system_tags : null, priority : 0; plugin_rule_key : URF_UNREAD_PUBLIC_OR_PROTECTED_FIELD

<h5>This field is never read.  The field is public or protected, so perhaps it is intended to be 
used with classes not seen as part of the analysis. If not, consider removing it from the class.</h5>

--------



## 293.


*  Dodgy - Vacuous bit mask operation on integer value

system_tags : null, priority : 3; plugin_rule_key : INT_VACUOUS_BIT_OPERATION

<h5> This is an integer bit operation (and, or, or exclusive or) that doesn't do any useful work
(e.g., <code>v & 0xffffffff</code>).

</h5>

--------



## 294.


*  Switch statement found where default case is missing

system_tags : null, priority : 2; plugin_rule_key : SF_SWITCH_NO_DEFAULT

<h5>
      This method contains a switch statement where default case is missing.
      Usually you need to provide a default case.
      </h5>

<p>
This rule is deprecated, use {rule:squid:SwitchLastCaseIsDefaultCheck} instead.
</p>

--------



## 295.


*  Boxing/unboxing to parse a primitive

system_tags : null, priority : 2; plugin_rule_key : DM_BOXED_PRIMITIVE_FOR_PARSING

<h5>
A boxed primitive is created from a String, just to extract the unboxed primitive value.
It is more efficient to just call the static parseXXX method.
</h5>

--------



## 296.


*  Correctness - An apparent infinite loop

system_tags : null, priority : 3; plugin_rule_key : IL_INFINITE_LOOP

<h5>This loop doesn't seem to have a way to terminate (other than by perhaps
throwing an exception).</h5>

--------



## 297.


*  Correctness - equals method compares class names rather than class objects

system_tags : null, priority : 2; plugin_rule_key : EQ_COMPARING_CLASS_NAMES

<h5> This method checks to see if two objects are the same class by checking to see if the names
of their classes are equal. You can have different classes with the same name if they are loaded by
different class loaders. Just check to see if the class objects are the same.
</h5>

--------



## 298.


*  Correctness - Null pointer dereference in method on exception path

system_tags : null, priority : 3; plugin_rule_key : NP_ALWAYS_NULL_EXCEPTION

<h5> A pointer which is null on an exception path is dereferenced here.&nbsp;
This will lead to a <code>NullPointerException</code> when the code is executed.&nbsp;
Note that because FindBugs currently does not prune infeasible exception paths,
this may be a false warning.</h5>

<p> Also note that FindBugs considers the default case of a switch statement to
be an exception path, since the default case is often infeasible.</p>

--------



## 299.


*  Dodgy - Method uses the same code for two branches

system_tags : null, priority : 3; plugin_rule_key : DB_DUPLICATE_BRANCHES

<h5>
      This method uses the same code to implement two branches of a conditional branch.
	Check to ensure that this isn't a coding mistake.
      </h5>

--------



## 300.


*  Bad practice - Dubious catching of IllegalMonitorStateException

system_tags : null, priority : 2; plugin_rule_key : IMSE_DONT_CATCH_IMSE

<h5>IllegalMonitorStateException is generally only
   thrown in case of a design flaw in your code (calling wait or
   notify on an object you do not hold a lock on).</h5>

--------



## 301.


*  Security - Servlet reflected cross site scripting vulnerability

system_tags : null, priority : 3; plugin_rule_key : XSS_REQUEST_PARAMETER_TO_SERVLET_WRITER

<h5>This code directly writes an HTTP parameter to Servlet output, which allows for a reflected cross site scripting
vulnerability. See <a href="http://en.wikipedia.org/wiki/Cross-site_scripting">http://en.wikipedia.org/wiki/Cross-site_scripting</a>
for more information.</h5>
<p>FindBugs looks only for the most blatant, obvious cases of cross site scripting.
If FindBugs found <em>any</em>, you <em>almost certainly</em> have more cross site scripting
vulnerabilities that FindBugs doesn't report. If you are concerned about cross site scripting, you should seriously 
consider using a commercial static analysis or pen-testing tool.
</p>

--------



## 302.


*  Dodgy - Code contains a hard coded reference to an absolute pathname

system_tags : null, priority : 3; plugin_rule_key : DMI_HARDCODED_ABSOLUTE_FILENAME

<h5>This code constructs a File object using a hard coded to an absolute pathname
(e.g., <code>new File("/home/dannyc/workspace/j2ee/src/share/com/sun/enterprise/deployment");</code>
</h5>

--------



## 303.


*  Bad practice - Class defines hashCode() but not equals()

system_tags : null, priority : 3; plugin_rule_key : HE_HASHCODE_NO_EQUALS

<h5> This class defines a <code>hashCode()</code> method but not an
  <code>equals()</code> method.&nbsp; Therefore, the class may
  violate the invariant that equal objects must have equal hashcodes.</h5>

<p>
This rule is deprecated, use {rule:squid:S1206} instead.
</p>

--------



## 304.


*  Correctness - Call to equals() comparing unrelated class and interface

system_tags : null, priority : 3; plugin_rule_key : EC_UNRELATED_CLASS_AND_INTERFACE

<h5>
This method calls equals(Object) on two references,  one of which is a class
and the other an interface, where neither the class nor any of its
non-abstract subclasses implement the interface.
Therefore, the objects being compared
are unlikely to be members of the same class at runtime
(unless some application classes were not analyzed, or dynamic class
loading can occur at runtime).
According to the contract of equals(),
objects of different
classes should always compare as unequal; therefore, according to the
contract defined by java.lang.Object.equals(Object),
the result of this comparison will always be false at runtime.
</h5>

--------



## 305.


*  Dodgy - Dereference of the result of readLine() without nullcheck

system_tags : null, priority : 3; plugin_rule_key : NP_DEREFERENCE_OF_READLINE_VALUE

<h5> The result of invoking readLine() is dereferenced without checking to see if the result is null. If there are no more lines of text
to read, readLine() will return null and dereferencing that will generate a null pointer exception.
</h5>

--------



## 306.


*  Correctness - Impossible cast

system_tags : null, priority : 4; plugin_rule_key : BC_IMPOSSIBLE_CAST

<h5>
This cast will always throw a ClassCastException.
</h5>

--------



## 307.


*  Correctness - Possible null pointer dereference in method on exception path

system_tags : null, priority : 3; plugin_rule_key : NP_NULL_ON_SOME_PATH_EXCEPTION

<h5> A reference value which is null on some exception control path is
dereferenced here.&nbsp; This may lead to a <code>NullPointerException</code>
when the code is executed.&nbsp;
Note that because FindBugs currently does not prune infeasible exception paths,
this may be a false warning.</h5>

<p> Also note that FindBugs considers the default case of a switch statement to
be an exception path, since the default case is often infeasible.</p>

--------



## 308.


*  Dodgy - Unsigned right shift cast to short/byte

system_tags : null, priority : 3; plugin_rule_key : ICAST_QUESTIONABLE_UNSIGNED_RIGHT_SHIFT

<h5>
The code performs an unsigned right shift, whose result is then
cast to a short or byte, which discards the upper bits of the result.
Since the upper bits are discarded, there may be no difference between
a signed and unsigned right shift (depending upon the size of the shift).
</h5>

--------



## 309.


*  Dodgy - Initialization circularity

system_tags : null, priority : 3; plugin_rule_key : IC_INIT_CIRCULARITY

<h5> A circularity was detected in the static initializers of the two
  classes referenced by the bug instance.&nbsp; Many kinds of unexpected
  behavior may arise from such circularity.</h5>

--------



## 310.


*  Performance - Method calls static Math class method on a constant value

system_tags : null, priority : 3; plugin_rule_key : UM_UNNECESSARY_MATH

<h5> This method uses a static method from java.lang.Math on a constant value. This method's
result in this case, can be determined statically, and is faster and sometimes more accurate to
just use the constant. Methods detected are:
</h5>
<table>
<tr>
   <th>Method</th> <th>Parameter</th>
</tr>
<tr>
   <td>abs</td> <td>-any-</td>
</tr>
<tr>
   <td>acos</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>asin</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>atan</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>atan2</td> <td>0.0</td>
</tr>
<tr>
   <td>cbrt</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>ceil</td> <td>-any-</td>
</tr>
<tr>
   <td>cos</td> <td>0.0</td>
</tr>
<tr>
   <td>cosh</td> <td>0.0</td>
</tr>
<tr>
   <td>exp</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>expm1</td> <td>0.0</td>
</tr>
<tr>
   <td>floor</td> <td>-any-</td>
</tr>
<tr>
   <td>log</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>log10</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>rint</td> <td>-any-</td>
</tr>
<tr>
   <td>round</td> <td>-any-</td>
</tr>
<tr>
   <td>sin</td> <td>0.0</td>
</tr>
<tr>
   <td>sinh</td> <td>0.0</td>
</tr>
<tr>
   <td>sqrt</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>tan</td> <td>0.0</td>
</tr>
<tr>
   <td>tanh</td> <td>0.0</td>
</tr>
<tr>
   <td>toDegrees</td> <td>0.0 or 1.0</td>
</tr>
<tr>
   <td>toRadians</td> <td>0.0</td>
</tr>
</table>

--------



## 311.


*  Class names should start with an upper case letter

system_tags : null, priority : 2; plugin_rule_key : NM_CLASS_NAMING_CONVENTION

<h5>
      Class names should be nouns, in mixed case with the first letter of each internal word capitalized. 
      Try to keep your class names simple and descriptive. Use whole words-avoid acronyms and abbreviations 
      (unless the abbreviation is much more widely used than the long form, such as URL or HTML).
      </h5>

<p>
This rule is deprecated, use {rule:squid:S00101} and {rule:squid:S00114} instead.
</p>

--------



## 312.


*  Correctness - Nullcheck of value previously dereferenced

system_tags : null, priority : 3; plugin_rule_key : RCN_REDUNDANT_NULLCHECK_WOULD_HAVE_BEEN_A_NPE

<h5> A value is checked here to see whether it is null, but this value can't
be null because it was previously dereferenced and if it were null a null pointer
exception would have occurred at the earlier dereference. 
Essentially, this code and the previous dereference
disagree as to whether this value is allowed to be null. Either the check is redundant
or the previous dereference is erroneous.</h5>

--------



## 313.


*  Dodgy - Class doesn't override equals in superclass

system_tags : null, priority : 2; plugin_rule_key : EQ_DOESNT_OVERRIDE_EQUALS

<h5> This class extends a class that defines an equals method and adds fields, but doesn't
define an equals method itself. Thus, equality on instances of this class will
ignore the identity of the subclass and the added fields. Be sure this is what is intended,
and that you don't need to override the equals method. Even if you don't need to override
the equals method, consider overriding it anyway to document the fact
that the equals method for the subclass just return the result of
invoking super.equals(o).
  </h5>

--------



## 314.


*  Self assignment of local rather than assignment to field

system_tags : null, priority : 2; plugin_rule_key : SA_LOCAL_SELF_ASSIGNMENT_INSTEAD_OF_FIELD

<h5>This method contains a self assignment of a local variable, and there is a field with an identical name.
Assignment appears to have been ; e.g.
<pre>
  int foo;
  public void setFoo(int foo) {
    foo = foo;
  }
</pre>
The assignment is useless. Did you mean to assign to the field instead?</h5>

<p>
This rule is deprecated, use {rule:squid:S1226} instead.
</p>

--------



## 315.


*  Class defines tostring(); should it be toString()?

system_tags : null, priority : 2; plugin_rule_key : NM_LCASE_TOSTRING

<h5>
      This class defines a method called <code>tostring()</code>.  
      This method does not override the <code>toString()</code> 
      method in <code>java.lang.Object</code>, which is probably what was intended.
      </h5>

--------



## 316.


*  Multithreaded correctness - A thread was created using the default empty run method

system_tags : null, priority : 2; plugin_rule_key : DM_USELESS_THREAD

<h5>This method creates a thread without specifying a run method either by deriving from the Thread class, or
  by passing a Runnable object. This thread, then, does nothing but waste time.
</h5>

--------



## 317.


*  Using monitor style wait methods on util.concurrent abstraction

system_tags : null, priority : 2; plugin_rule_key : JML_JSR166_CALLING_WAIT_RATHER_THAN_AWAIT

<h5>This method calls <code>wait()</code>, <code>notify()</code> or <code>notifyAll()</code> on an object that also 
provides an <code>await()</code>, <code>signal()</code>, <code>signalAll()</code> method (such as util.concurrent 
Condition objects). This probably isn't what you want, and even if you do want it, you should consider changing your 
design, as other developers will find it exceptionally confusing.</h5>

--------



## 318.


*  Bad practice - Finalizer nullifies superclass finalizer

system_tags : null, priority : 3; plugin_rule_key : FI_NULLIFY_SUPER

<h5> This empty <code>finalize()</code> method explicitly negates the
  effect of any finalizer defined by its superclass.&nbsp; Any finalizer
  actions defined for the superclass will not be performed.&nbsp;
  Unless this is intended, delete this method.</h5>

--------



## 319.


*  Malicious code vulnerability - Field is a mutable Hashtable

system_tags : null, priority : 2; plugin_rule_key : MS_MUTABLE_HASHTABLE

<h5>A final static field references a Hashtable
   and can be accessed by malicious code or
        by accident from another package.
   This code can freely modify the contents of the Hashtable.</h5>

--------



## 320.


*  Bad practice - Confusing method names

system_tags : null, priority : 2; plugin_rule_key : NM_CONFUSING

<h5> The referenced methods have names that differ only by capitalization.</h5>

--------



## 321.


*  Performance - Method allocates an object, only to get the class object

system_tags : null, priority : 2; plugin_rule_key : DM_NEW_FOR_GETCLASS

<h5>This method allocates an object just to call getClass() on it, in order to
  retrieve the Class object for it. It is simpler to just access the .class property of the class.</h5>

--------



## 322.


*  Dodgy - Computation of average could overflow

system_tags : null, priority : 3; plugin_rule_key : IM_AVERAGE_COMPUTATION_COULD_OVERFLOW

<h5>The code computes the average of two integers using either division or signed right shift,
and then uses the result as the index of an array.
If the values being averaged are very large, this can overflow (resulting in the computation
of a negative average).  Assuming that the result is intended to be nonnegative, you 
can use an unsigned right shift instead. In other words, rather that using <code>(low+high)/2</code>,
use <code>(low+high) &gt;&gt;&gt; 1</code>
</h5>
<p>This bug exists in many earlier implementations of binary search and merge sort.
Martin Buchholz <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6412541">found and fixed it</a>
in the JDK libraries, and Joshua Bloch
<a href="http://googleresearch.blogspot.com/2006/06/extra-extra-read-all-about-it-nearly.html">widely
publicized the bug pattern</a>.
</p>

--------



## 323.


*  Bad practice - Non-serializable class has a serializable inner class

system_tags : null, priority : 1; plugin_rule_key : SE_BAD_FIELD_INNER_CLASS

<h5> This Serializable class is an inner class of a non-serializable class.
Thus, attempts to serialize it will also attempt to associate instance of the outer
class with which it is associated, leading to a runtime error.
</h5>
<p>If possible, making the inner class a static inner class should solve the 
problem. Making the outer class serializable might also work, but that would
mean serializing an instance of the inner class would always also serialize the instance
of the outer class, which it often not what you really want.

--------



## 324.


*  Correctness - Read of unwritten field

system_tags : null, priority : 2; plugin_rule_key : NP_UNWRITTEN_FIELD

<h5>The program is dereferencing a field that does not seem to ever have a non-null value written to it. Dereferencing this value will generate a null pointer exception.</h5>

--------



## 325.


*  Bad practice - Method ignores exceptional return value

system_tags : null, priority : 2; plugin_rule_key : RV_RETURN_VALUE_IGNORED_BAD_PRACTICE

<h5> This method returns a value that is not checked. The return value should be checked
since it can indicate an unusual or unexpected function execution. For
example, the <code>File.delete()</code> method returns false
if the file could not be successfully deleted (rather than 
throwing an Exception).
If you don't check the result, you won't notice if the method invocation
signals unexpected behavior by returning an atypical return value.
</h5>

--------



## 326.


*  Comparing values with incompatible type qualifiers

system_tags : null, priority : 2; plugin_rule_key : TQ_COMPARING_VALUES_WITH_INCOMPATIBLE_TYPE_QUALIFIERS

<h5>
A value specified as carrying a type qualifier annotation is
compared with a value that doesn't ever carry that qualifier.
</h5>

<p>
More precisely, a value annotated with a type qualifier specifying when=ALWAYS
is compared with a value that where the same type qualifier specifies when=NEVER.
</p>

<p>
For example, say that @NonNegative is a nickname for
the type qualifier annotation @Negative(when=When.NEVER).
The following code will generate this warning because
the return statement requires a @NonNegative value,
but receives one that is marked as @Negative.
</p>
<pre>
public boolean example(@Negative Integer value1, @NonNegative Integer value2) {
  return value1.equals(value2);
}
</pre>

--------



## 327.


*  Bad practice - Suspicious reference comparison

system_tags : null, priority : 3; plugin_rule_key : RC_REF_COMPARISON

<h5> This method compares two reference values using the == or != operator,
where the correct way to compare instances of this type is generally
with the equals() method.  Examples of classes which should generally
not be compared by reference are java.lang.Integer, java.lang.Float, etc.</h5>

--------



## 328.


*  Correctness - Class defines field that masks a superclass field

system_tags : null, priority : 2; plugin_rule_key : MF_CLASS_MASKS_FIELD

<h5> This class defines a field with the same name as a visible
instance field in a superclass.  This is confusing, and
may indicate an error if methods update or access one of
the fields when they wanted the other.</h5>

--------



## 329.


*  Dodgy - Class exposes synchronization and semaphores in its public interface

system_tags : null, priority : 3; plugin_rule_key : PS_PUBLIC_SEMAPHORES

<h5>
    This class uses synchronization along with wait(), notify() or notifyAll() on itself (the this
    reference). Client classes that use this class, may, in addition, use an instance of this class
    as a synchronizing object. Because two classes are using the same object for synchronization,
    Multithread correctness is suspect. You should not synchronize nor call semaphore methods on
    a public reference. Consider using a internal private member variable to control synchronization.
    </h5>

--------



## 330.


*  Dodgy - Class too big for analysis

system_tags : null, priority : 1; plugin_rule_key : SKIPPED_CLASS_TOO_BIG

<h5>This class is bigger than can be effectively handled, and was not fully analyzed for errors.
</h5>

--------



## 331.


*  Performance - Huge string constants is duplicated across multiple class files

system_tags : null, priority : 3; plugin_rule_key : HSC_HUGE_SHARED_STRING_CONSTANT

<h5>
	A large String constant is duplicated across multiple class files. 
	This is likely because a final field is initialized to a String constant, and the Java language
	mandates that all references to a final field from other classes be inlined into
that classfile. See <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6447475">JDK bug 6447475</a>
	for a description of an occurrence of this bug in the JDK and how resolving it reduced
	the size of the JDK by 1 megabyte.
</h5>

--------



## 332.


*  Bad practice - Class is Serializable but its superclass doesn't define a void constructor

system_tags : null, priority : 2; plugin_rule_key : SE_NO_SUITABLE_CONSTRUCTOR

<h5> This class implements the <code>Serializable</code> interface
   and its superclass does not. When such an object is deserialized,
   the fields of the superclass need to be initialized by
   invoking the void constructor of the superclass.
   Since the superclass does not have one,
   serialization and deserialization will fail at runtime.</h5>

--------



## 333.


*  Multithreaded correctness - Mismatched notify()

system_tags : null, priority : 3; plugin_rule_key : MWN_MISMATCHED_NOTIFY

<h5> This method calls Object.notify() or Object.notifyAll() without obviously holding a lock
on the object.&nbsp;  Calling notify() or notifyAll() without a lock held will result in
an <code>IllegalMonitorStateException</code> being thrown.</h5>

--------



## 334.


*  Multithreaded correctness - Call to static DateFormat

system_tags : null, priority : 3; plugin_rule_key : STCAL_INVOKE_ON_STATIC_DATE_FORMAT_INSTANCE

<h5>As the JavaDoc states, DateFormats are inherently unsafe for multithreaded use. 
The detector has found a call to an instance of DateFormat that has been obtained via a static
field. This looks suspicous.</h5>
<p>For more information on this see <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6231579">Sun Bug #6231579</a>
and <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6178997">Sun Bug #6178997</a>.</p>

--------



## 335.


*  Dodgy - Double assignment of local variable

system_tags : null, priority : 3; plugin_rule_key : SA_LOCAL_DOUBLE_ASSIGNMENT

<h5> This method contains a double assignment of a local variable; e.g.
</h5>
<pre>
  public void foo() {
    int x,y;
    x = x = 17;
  }
</pre>
<p>Assigning the same value to a variable twice is useless, and may indicate a logic error or typo.</p>

--------



## 336.


*  Bad practice - Method invoked that should be only be invoked inside a doPrivileged block

system_tags : null, priority : 2; plugin_rule_key : DP_DO_INSIDE_DO_PRIVILEGED

<h5> This code invokes a method that requires a security permission check.
  If this code will be granted security permissions, but might be invoked by code that does not
  have security permissions, then the invocation needs to occur inside a doPrivileged block.</h5>

--------



## 337.


*  Correctness - Method ignores return value

system_tags : null, priority : 2; plugin_rule_key : RV_RETURN_VALUE_IGNORED2

<h5> The return value of this method should be checked. One common
cause of this warning is to invoke a method on an immutable object,
thinking that it updates the object. For example, in the following code
fragment,</h5>
<blockquote>
<pre>
String dateString = getHeaderField(name);
dateString.trim();
</pre>
</blockquote>
<p>the programmer seems to be thinking that the trim() method will update
the String referenced by dateString. But since Strings are immutable, the trim()
function returns a new String value, which is being ignored here. The code
should be corrected to: </p>
<blockquote>
<pre>
String dateString = getHeaderField(name);
dateString = dateString.trim();
</pre>
</blockquote>

--------



## 338.


*  Correctness - Very confusing method names

system_tags : null, priority : 2; plugin_rule_key : NM_VERY_CONFUSING

<h5> The referenced methods have names that differ only by capitalization. 
This is very confusing because if the capitalization were
identical then one of the methods would override the other.
</h5>

--------



## 339.


*  Correctness - Doomed attempt to append to an object output stream

system_tags : null, priority : 3; plugin_rule_key : IO_APPENDING_TO_OBJECT_OUTPUT_STREAM

<h5>
     This code opens a file in append mode and then wraps the result in an object output stream. 
     This won't allow you to append to an existing object output stream stored in a file. If you want to be
     able to append to an object output stream, you need to keep the object output stream open.
      </h5>
      <p>The only situation in which opening a file in append mode and the writing an object output stream
      could work is if on reading the file you plan to open it in random access mode and seek to the byte offset
      where the append started.
      </p> 
      
      <p>
      TODO: example.
      </p>

--------



## 340.


*  Bad practice - Method invokes dangerous method runFinalizersOnExit

system_tags : null, priority : 2; plugin_rule_key : DM_RUN_FINALIZERS_ON_EXIT

<h5> <em>Never call System.runFinalizersOnExit
or Runtime.runFinalizersOnExit for any reason: they are among the most
dangerous methods in the Java libraries.</em> -- Joshua Bloch</h5>

--------



## 341.


*  Multithreaded correctness - Static DateFormat

system_tags : null, priority : 3; plugin_rule_key : STCAL_STATIC_SIMPLE_DATE_FORMAT_INSTANCE

<h5>As the JavaDoc states, DateFormats are inherently unsafe for multithreaded use. 
Sharing a single instance across thread boundaries without proper synchronization will result in erratic behavior of the
application.</h5>
<p>You may also experience serialization problems.</p>
<p>Using an instance field is recommended.</p>
<p>For more information on this see <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6231579">Sun Bug #6231579</a>
and <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6178997">Sun Bug #6178997</a>.</p>

--------



## 342.


*  Bad practice - Finalizer nulls fields

system_tags : null, priority : 2; plugin_rule_key : FI_FINALIZER_NULLS_FIELDS

<h5> This finalizer nulls out fields.  This is usually an error, as it does not aid garbage collection,
  and the object is going to be garbage collected anyway.

--------



## 343.


*  Correctness - Doomed test for equality to NaN

system_tags : null, priority : 3; plugin_rule_key : FE_TEST_IF_EQUAL_TO_NOT_A_NUMBER

<h5>
    This code checks to see if a floating point value is equal to the special
	Not A Number value (e.g., <code>if (x == Double.NaN)</code>). However,
	because of the special semantics of <code>NaN</code>, no value
	is equal to <code>Nan</code>, including <code>NaN</code>. Thus,
	<code>x == Double.NaN</code> always evaluates to false.

	To check to see if a value contained in <code>x</code>
	is the special Not A Number value, use 
	<code>Double.isNaN(x)</code> (or <code>Float.isNaN(x)</code> if
	<code>x</code> is floating point precision).
    </h5>

--------



## 344.


*  Multithreaded correctness - Wait with two locks held

system_tags : null, priority : 2; plugin_rule_key : TLW_TWO_LOCK_WAIT

<h5> Waiting on a monitor while two locks are held may cause
  deadlock.
   &nbsp;
   Performing a wait only releases the lock on the object
   being waited on, not any other locks.
   &nbsp;
This not necessarily a bug, but is worth examining
  closely.</h5>

--------



## 345.


*  Security - Hardcoded constant database password

system_tags : null, priority : 4; plugin_rule_key : DMI_CONSTANT_DB_PASSWORD

<h5>This code creates a database connect using a hardcoded, constant password. Anyone with access to either the source code or the compiled code can 
	easily learn the password.
</h5>

--------



## 346.


*  Reversed method arguments

system_tags : null, priority : 1; plugin_rule_key : DMI_ARGUMENTS_WRONG_ORDER

<h5>The arguments to this method call seem to be in the wrong order. For example, a call 
<code>Preconditions.checkNotNull("message", message)</code> has reserved arguments: the value 
to be checked is the first argument.</h5>

--------



## 347.


*  Performance - Maps and sets of URLs can be performance hogs

system_tags : null, priority : 4; plugin_rule_key : DMI_COLLECTION_OF_URLS

<h5> This method or field is or uses a Map or Set of URLs. Since both the equals and hashCode
method of URL perform domain name resolution, this can result in a big performance hit.
See <a href="http://michaelscharf.blogspot.com/2006/11/javaneturlequals-and-hashcode-make.html">http://michaelscharf.blogspot.com/2006/11/javaneturlequals-and-hashcode-make.html</a> for more information.
Consider using <code>java.net.URI</code> instead.
   </h5>

--------



## 348.


*  Method names should start with a lower case letter

system_tags : null, priority : 2; plugin_rule_key : NM_METHOD_NAMING_CONVENTION

<h5>
      Methods should be verbs, in mixed case with the first letter lowercase, 
      with the first letter of each internal word capitalized.
      </h5>

<p>
This rule is deprecated, use {rule:squid:S00100} instead.
</p>

--------



## 349.


*  Correctness - Deadly embrace of non-static inner class and thread local

system_tags : null, priority : 2; plugin_rule_key : SIC_THREADLOCAL_DEADLY_EMBRACE

This class is an inner class, but should probably be a static inner class. As it is, there is a serious danger of a deadly embrace between the inner class and the thread local in the outer class. Because the inner class isn't static, it retains a reference to the outer class. If the thread local contains a reference to an instance of the inner class, the inner and outer instance will both be reachable and not eligible for garbage collection.

--------



## 350.


*  Bad practice - Method doesn't override method in superclass due to wrong package for parameter

system_tags : null, priority : 2; plugin_rule_key : NM_WRONG_PACKAGE_INTENTIONAL

<h5> The method in the subclass doesn't override a similar method in a superclass because the type of a parameter doesn't exactly match
the type of the corresponding parameter in the superclass. For example, if you have:</h5>

<blockquote>
<pre>
import alpha.Foo;
public class A {
  public int f(Foo x) { return 17; }
}
----
import beta.Foo;
public class B extends A {
  public int f(Foo x) { return 42; }
  public int f(alpha.Foo x) { return 27; }
}
</pre>
</blockquote>

<p>The <code>f(Foo)</code> method defined in class <code>B</code> doesn't
override the 
<code>f(Foo)</code> method defined in class <code>A</code>, because the argument
types are <code>Foo</code>'s from different packages.
</p>

<p>In this case, the subclass does define a method with a signature identical to the method in the superclass,
so this is presumably understood. However, such methods are exceptionally confusing. You should strongly consider
removing or deprecating the method with the similar but not identical signature.
</p>

--------



## 351.


*  Correctness - Integer remainder modulo 1

system_tags : null, priority : 3; plugin_rule_key : INT_BAD_REM_BY_1

<h5> Any expression (exp % 1) is guaranteed to always return zero.
Did you mean (exp &amp; 1) or (exp % 2) instead?
</h5>

--------



## 352.


*  Bad practice - Comparison of String objects using == or !=

system_tags : null, priority : 2; plugin_rule_key : ES_COMPARING_STRINGS_WITH_EQ

<h5>This code compares <code>java.lang.String</code> objects for reference
equality using the == or != operators.
Unless both strings are either constants in a source file, or have been
interned using the <code>String.intern()</code> method, the same string
value may be represented by two different String objects. Consider
using the <code>equals(Object)</code> method instead.</h5>

--------



## 353.


*  Dodgy - Complicated, subtle or wrong increment in for-loop

system_tags : null, priority : 3; plugin_rule_key : QF_QUESTIONABLE_FOR_LOOP

<h5>Are you sure this for loop is incrementing the correct variable?
   It appears that another variable is being initialized and checked
   by the for loop.
</h5>

--------



## 354.


*  Dodgy - Non-Boolean argument formatted using %b format specifier

system_tags : null, priority : 2; plugin_rule_key : VA_FORMAT_STRING_BAD_CONVERSION_TO_BOOLEAN

<h5>
An argument not of type Boolean is being formatted with a %b format specifier. This won't throw an
exception; instead, it will print true for any nonnull value, and false for null.
This feature of format strings is strange, and may not be what you intended.
</h5>

--------



## 355.


*  Dodgy - Method directly allocates a specific implementation of xml interfaces

system_tags : null, priority : 3; plugin_rule_key : XFB_XML_FACTORY_BYPASS

<h5>
      This method allocates a specific implementation of an xml interface. It is preferable to use
      the supplied factory classes to create these objects so that the implementation can be
      changed at runtime. See
      </h5>
      <ul>
         <li>javax.xml.parsers.DocumentBuilderFactory</li>
         <li>javax.xml.parsers.SAXParserFactory</li>
         <li>javax.xml.transform.TransformerFactory</li>
         <li>org.w3c.dom.Document.create<i>XXXX</i></li>
      </ul>
      <p>for details.</p>

--------



## 356.


*  Multithreaded correctness - Class's writeObject() method is synchronized but nothing else is

system_tags : null, priority : 3; plugin_rule_key : WS_WRITEOBJECT_SYNC

<h5> This class has a <code>writeObject()</code> method which is synchronized;
  however, no other method of the class is synchronized.</h5>

--------



## 357.


*  Bad practice - clone method does not call super.clone()

system_tags : null, priority : 2; plugin_rule_key : CN_IDIOM_NO_SUPER_CALL

<h5> This non-final class defines a clone() method that does not call super.clone().
If this class ("<i>A</i>") is extended by a subclass ("<i>B</i>"),
and the subclass <i>B</i> calls super.clone(), then it is likely that
<i>B</i>'s clone() method will return an object of type <i>A</i>,
which violates the standard contract for clone().</h5>

<p> If all clone() methods call super.clone(), then they are guaranteed
to use Object.clone(), which always returns an object of the correct type.</p>

<p>
This rule is deprecated, use {rule:squid:S1182} instead.
</p>

--------



## 358.


*  Correctness - Dead store of class literal

system_tags : null, priority : 3; plugin_rule_key : DLS_DEAD_STORE_OF_CLASS_LITERAL

<h5>
This instruction assigns a class literal to a variable and then never uses it.
<a href="//java.sun.com/j2se/1.5.0/compatibility.html#literal">The behavior of this differs in Java 1.4 and in Java 5.</a>
In Java 1.4 and earlier, a reference to <code>Foo.class</code> would force the static initializer
for <code>Foo</code> to be executed, if it has not been executed already.
In Java 5 and later, it does not.
</h5>
<p>See Sun's <a href="//java.sun.com/j2se/1.5.0/compatibility.html#literal">article on Java SE compatibility</a>
for more details and examples, and suggestions on how to force class initialization in Java 5.
</p>

--------



## 359.


*  Bad practice - Equals method should not assume anything about the type of its argument

system_tags : null, priority : 3; plugin_rule_key : BC_EQUALS_METHOD_SHOULD_WORK_FOR_ALL_OBJECTS

<h5>
The <code>equals(Object o)</code> method shouldn't make any assumptions
about the type of <code>o</code>. It should simply return
false if <code>o</code> is not the same type as <code>this</code>.
</h5>

--------



## 360.


*  Multithreaded correctness - Synchronization on field in futile attempt to guard that field

system_tags : null, priority : 2; plugin_rule_key : ML_SYNC_ON_FIELD_TO_GUARD_CHANGING_THAT_FIELD

<h5> This method synchronizes on a field in what appears to be an attempt
to guard against simultaneous updates to that field. But guarding a field
gets a lock on the referenced object, not on the field. This may not 
provide the mutual exclusion you need, and other threads might 
be obtaining locks on the referenced objects (for other purposes). An example
of this pattern would be:

<p><pre>
private Long myNtfSeqNbrCounter = new Long(0);
private Long getNotificationSequenceNumber() {
     Long result = null;
     synchronized(myNtfSeqNbrCounter) {
         result = new Long(myNtfSeqNbrCounter.longValue() + 1);
         myNtfSeqNbrCounter = new Long(result.longValue());
     }
     return result;
 }
</pre>


</h5>

--------



## 361.


*  Multithreaded correctness - Mismatched wait()

system_tags : null, priority : 3; plugin_rule_key : MWN_MISMATCHED_WAIT

<h5> This method calls Object.wait() without obviously holding a lock
on the object.&nbsp;  Calling wait() without a lock held will result in
an <code>IllegalMonitorStateException</code> being thrown.</h5>

--------



## 362.


*  Performance - Use the nextInt method of Random rather than nextDouble to generate a random integer

system_tags : null, priority : 2; plugin_rule_key : DM_NEXTINT_VIA_NEXTDOUBLE

<h5>If <code>r</code> is a <code>java.util.Random</code>, you can generate a random number from <code>0</code> to <code>n-1</code>
using <code>r.nextInt(n)</code>, rather than using <code>(int)(r.nextDouble() * n)</code>.
</h5>

--------



## 363.


*  Sequence of calls to concurrent abstraction may not be atomic

system_tags : null, priority : 2; plugin_rule_key : AT_OPERATION_SEQUENCE_ON_CONCURRENT_ABSTRACTION

<h5>This code contains a sequence of calls to a concurrent abstraction (such as a concurrent hash map). These calls will not be executed atomically.</h5>

--------



## 364.


*  Dodgy - Dead store of null to local variable

system_tags : null, priority : 3; plugin_rule_key : DLS_DEAD_LOCAL_STORE_OF_NULL

<h5>The code stores null into a local variable, and the stored value is not
read. This store may have been introduced to assist the garbage collector, but
as of Java SE 6.0, this is no longer needed or useful.
</h5>

--------



## 365.


*  Performance - The equals and hashCode methods of URL are blocking

system_tags : null, priority : 4; plugin_rule_key : DMI_BLOCKING_METHODS_ON_URL

<h5> The equals and hashCode
method of URL perform domain name resolution, this can result in a big performance hit.
See <a href="http://michaelscharf.blogspot.com/2006/11/javaneturlequals-and-hashcode-make.html">http://michaelscharf.blogspot.com/2006/11/javaneturlequals-and-hashcode-make.html</a> for more information.
Consider using <code>java.net.URI</code> instead.
   </h5>

--------



## 366.


*  Dodgy - Possible null pointer dereference on path that might be infeasible

system_tags : null, priority : 3; plugin_rule_key : NP_NULL_ON_SOME_PATH_MIGHT_BE_INFEASIBLE

<h5> There is a branch of statement that, <em>if executed,</em>  guarantees that
a null value will be dereferenced, which
would generate a <code>NullPointerException</code> when the code is executed.
Of course, the problem might be that the branch or statement is infeasible and that
the null pointer exception can't ever be executed; deciding that is beyond the ability of FindBugs.
Due to the fact that this value had been previously tested for nullness, this is a definite possibility.
</h5>

--------



## 367.


*  Absolute path traversal in servlet

system_tags : null, priority : 2; plugin_rule_key : PT_ABSOLUTE_PATH_TRAVERSAL

<h5>
The software uses an HTTP request parameter to construct a pathname that should be within a restricted directory,
but it does not properly neutralize absolute path sequences such as "/abs/path" that can resolve to a location that is outside of that directory.

See <a href="http://cwe.mitre.org/data/definitions/36.html">http://cwe.mitre.org/data/definitions/36.html</a> for more information.
</h5>

<p>
FindBugs looks only for the most blatant, obvious cases of absolute path traversal.
If FindBugs found <em>any</em>, you <em>almost certainly</em> have more
vulnerabilities that FindBugs doesn't report. If you are concerned about absolute path traversal, you should seriously
consider using a commercial static analysis or pen-testing tool.
</p>

--------



## 368.


*  Bad practice - Very confusing method names (but perhaps intentional)

system_tags : null, priority : 2; plugin_rule_key : NM_VERY_CONFUSING_INTENTIONAL

<h5> The referenced methods have names that differ only by capitalization. 
This is very confusing because if the capitalization were
identical then one of the methods would override the other. From the existence of other methods, it
seems that the existence of both of these methods is intentional, but is sure is confusing. 
You should try hard to eliminate one of them, unless you are forced to have both due to frozen APIs.
</h5>

--------



## 369.


*  Security - Servlet reflected cross site scripting vulnerability

system_tags : null, priority : 3; plugin_rule_key : XSS_REQUEST_PARAMETER_TO_SEND_ERROR

<h5>This code directly writes an HTTP parameter to a Server error page (using HttpServletResponse.sendError). Echoing this untrusted input allows
for a reflected cross site scripting
vulnerability. See <a href="http://en.wikipedia.org/wiki/Cross-site_scripting">http://en.wikipedia.org/wiki/Cross-site_scripting</a>
for more information.</h5>
<p>FindBugs looks only for the most blatant, obvious cases of cross site scripting.
If FindBugs found <em>any</em>, you <em>almost certainly</em> have more cross site scripting
vulnerabilities that FindBugs doesn't report. If you are concerned about cross site scripting, you should seriously 
consider using a commercial static analysis or pen-testing tool.
</p>

--------



## 370.


*  Dodgy - private readResolve method not inherited by subclasses

system_tags : null, priority : 2; plugin_rule_key : SE_PRIVATE_READ_RESOLVE_NOT_INHERITED

<h5> This class defines a private readResolve method. Since it is private, it won't be inherited by subclasses.
This might be intentional and OK, but should be reviewed to ensure it is what is intended.
</h5>

--------



## 371.


*  Correctness - Invocation of toString on an array

system_tags : null, priority : 3; plugin_rule_key : DMI_INVOKING_TOSTRING_ON_ARRAY

<h5>
The code invokes toString on an array, which will generate a fairly useless result
such as [C@16f0472. Consider using Arrays.toString to convert the array into a readable
String that gives the contents of the array. See Programming Puzzlers, chapter 3, puzzle 12.
</h5>

--------



## 372.


*  Correctness - Method does not check for null argument

system_tags : null, priority : 2; plugin_rule_key : NP_ARGUMENT_MIGHT_BE_NULL

<h5>
	A parameter to this method has been identified as a value that should
	always be checked to see whether or not it is null, but it is being dereferenced
	without a preceding null check.
      </h5>

--------



## 373.


*  Bad practice - Abstract class defines covariant compareTo() method

system_tags : null, priority : 2; plugin_rule_key : CO_ABSTRACT_SELF

<h5> This class defines a covariant version of <code>compareTo()</code>.&nbsp;
  To correctly override the <code>compareTo()</code> method in the
  <code>Comparable</code> interface, the parameter of <code>compareTo()</code>
  must have type <code>java.lang.Object</code>.</h5>

--------



## 374.


*  Bad practice - Method invokes System.exit(...)

system_tags : null, priority : 2; plugin_rule_key : DM_EXIT

<h5> Invoking System.exit shuts down the entire Java virtual machine. This
   should only been done when it is appropriate. Such calls make it
   hard or impossible for your code to be invoked by other code.
   Consider throwing a RuntimeException instead.</h5>

<p>
This rule is deprecated, use {rule:squid:S1147} instead.
</p>

--------



## 375.


*  Correctness - Return value of putIfAbsent ignored, value passed to putIfAbsent reused

system_tags : null, priority : 2; plugin_rule_key : RV_RETURN_VALUE_OF_PUTIFABSENT_IGNORED

The putIfAbsent method is typically used to ensure that a single value is associated with a given key (the first value for which put if absent succeeds). If you ignore the return value and retain a reference to the value passed in, you run the risk of retaining a value that is not the one that is associated with the key in the map. If it matters which one you use and you use the one that isn't stored in the map, your program will behave incorrectly.

--------



## 376.


*  Multithreaded correctness - Method does not release lock on all exception paths

system_tags : null, priority : 3; plugin_rule_key : UL_UNRELEASED_LOCK_EXCEPTION_PATH

<h5> This method acquires a JSR-166 (<code>java.util.concurrent</code>) lock,
but does not release it on all exception paths out of the method.  In general, the correct idiom
for using a JSR-166 lock is:
</h5>
<pre>
    Lock l = ...;
    l.lock();
    try {
        // do something
    } finally {
        l.unlock();
    }
</pre>

--------



## 377.


*  Non-transient non-serializable instance field in serializable class

system_tags : null, priority : 2; plugin_rule_key : SE_BAD_FIELD

<h5>
      This Serializable class defines a non-primitive instance field which is neither transient, 
      Serializable, or <code>java.lang.Object</code>, and does not appear to implement the <code>Externalizable</code> 
      interface or the <code>readObject()</code> and <code>writeObject()</code> methods.  
      Objects of this class will not be deserialized correctly if a non-Serializable object is stored in this field.
      </h5>

--------



## 378.


*  Dodgy - Self assignment of local variable

system_tags : null, priority : 3; plugin_rule_key : SA_LOCAL_SELF_ASSIGNMENT

<h5> This method contains a self assignment of a local variable; e.g.</h5>
<pre>
  public void foo() {
    int x = 3;
    x = x;
  }
</pre>
<p>
Such assignments are useless, and may indicate a logic error or typo.
</p>

--------



## 379.


*  Read of unwritten public or protected field

system_tags : null, priority : 2; plugin_rule_key : NP_UNWRITTEN_PUBLIC_OR_PROTECTED_FIELD

<h5>The program is dereferencing a public or protected field that does not seem to ever have a non-null
 value written to it. Unless the field is initialized via some mechanism not seen by the analysis, 
 dereferencing this value will generate a null pointer exception.</h5>

--------



## 380.


*  Bad practice - Method ignores results of InputStream.read()

system_tags : null, priority : 2; plugin_rule_key : RR_NOT_CHECKED

<h5> This method ignores the return value of one of the variants of
  <code>java.io.InputStream.read()</code> which can return multiple bytes.&nbsp;
  If the return value is not checked, the caller will not be able to correctly
  handle the case where fewer bytes were read than the caller requested.&nbsp;
  This is a particularly insidious kind of bug, because in many programs,
  reads from input streams usually do read the full amount of data requested,
  causing the program to fail only sporadically.</h5>

--------



## 381.


*  Dodgy - Write to static field from instance method

system_tags : null, priority : 3; plugin_rule_key : ST_WRITE_TO_STATIC_FROM_INSTANCE_METHOD

<h5> This instance method writes to a static field. This is tricky to get
correct if multiple instances are being manipulated,
and generally bad practice.
</h5>

--------



## 382.


*  Bad practice - Covariant equals() method defined

system_tags : null, priority : 2; plugin_rule_key : EQ_SELF_NO_OBJECT

<h5> This class defines a covariant version of <code>equals()</code>.&nbsp;
  To correctly override the <code>equals()</code> method in
  <code>java.lang.Object</code>, the parameter of <code>equals()</code>
  must have type <code>java.lang.Object</code>.</h5>

<p>
This rule is deprecated, use {rule:squid:S1201} instead.
</p>

--------



## 383.


*  Bad practice - toString method may return null

system_tags : null, priority : 3; plugin_rule_key : NP_TOSTRING_COULD_RETURN_NULL

<h5>
	This toString method seems to return null in some circumstances. A liberal reading of the
	spec could be interpreted as allowing this, but it is probably a bad idea and could cause
	other code to break. Return the empty string or some other appropriate string rather than null.
      </h5>

--------



## 384.


*  Correctness - No relationship between generic parameter and method argument

system_tags : null, priority : 3; plugin_rule_key : GC_UNRELATED_TYPES

<h5> This call to a generic collection method contains an argument
     with an incompatible class from that of the collection's parameter
	(i.e., the type of the argument is neither a supertype nor a subtype 
		of the corresponding generic type argument).
     Therefore, it is unlikely that the collection contains any objects 
	that are equal to the method argument used here.
	Most likely, the wrong value is being passed to the method.</h5>
	<p>In general, instances of two unrelated classes are not equal. 
	For example, if the <code>Foo</code> and <code>Bar</code> classes
	are not related by subtyping, then an instance of <code>Foo</code>
		should not be equal to an instance of <code>Bar</code>.
	Among other issues, doing so will likely result in an equals method
	that is not symmetrical. For example, if you define the <code>Foo</code> class
	so that a <code>Foo</code> can be equal to a <code>String</code>,
	your equals method isn't symmetrical since a <code>String</code> can only be equal
	to a <code>String</code>.
	</p>
	<p>In rare cases, people do define nonsymmetrical equals methods and still manage to make 
	their code work. Although none of the APIs document or guarantee it, it is typically
	the case that if you check if a <code>Collection&lt;String&gt;</code> contains
	a <code>Foo</code>, the equals method of argument (e.g., the equals method of the 
	<code>Foo</code> class) used to perform the equality checks.
	</p>

--------



## 385.


*  Correctness - An apparent infinite recursive loop

system_tags : null, priority : 3; plugin_rule_key : IL_INFINITE_RECURSIVE_LOOP

<h5>This method unconditionally invokes itself. This would seem to indicate
an infinite recursive loop that will result in a stack overflow.</h5>

--------



## 386.


*  Performance - Method invokes toString() method on a String

system_tags : null, priority : 0; plugin_rule_key : DM_STRING_TOSTRING

<h5> Calling <code>String.toString()</code> is just a redundant operation.
  Just use the String.</h5>

--------



## 387.


*  Bad practice - Creates an empty zip file entry

system_tags : null, priority : 2; plugin_rule_key : AM_CREATES_EMPTY_ZIP_FILE_ENTRY

<h5>The code calls <code>putNextEntry()</code>, immediately
followed by a call to <code>closeEntry()</code>. This results
in an empty ZipFile entry. The contents of the entry
should be written to the ZipFile between the calls to
<code>putNextEntry()</code> and
<code>closeEntry()</code>.</h5>

--------



## 388.


*  Dodgy - Questionable use of non-short-circuit logic

system_tags : null, priority : 2; plugin_rule_key : NS_NON_SHORT_CIRCUIT

<h5> This code seems to be using non-short-circuit logic (e.g., &amp;
or |)
rather than short-circuit logic (&amp;&amp; or ||).
Non-short-circuit logic causes both sides of the expression
to be evaluated even when the result can be inferred from
knowing the left-hand side. This can be less efficient and
can result in errors if the left-hand side guards cases
when evaluating the right-hand side can generate an error.

<p>See <a href="http://java.sun.com/docs/books/jls/third_edition/html/expressions.html#15.22.2">the Java
Language Specification</a> for details

</h5>

--------



## 389.


*  Performance - Method invokes inefficient Boolean constructor; use Boolean.valueOf(...) instead

system_tags : null, priority : 2; plugin_rule_key : DM_BOOLEAN_CTOR

<h5> Creating new instances of <code>java.lang.Boolean</code> wastes
  memory, since <code>Boolean</code> objects are immutable and there are
  only two useful values of this type.&nbsp; Use the <code>Boolean.valueOf()</code>
  method (or Java 1.5 autoboxing) to create <code>Boolean</code> objects instead.</h5>

--------



## 390.


*  Dodgy - Questionable cast to concrete collection

system_tags : null, priority : 3; plugin_rule_key : BC_BAD_CAST_TO_CONCRETE_COLLECTION

<h5>
This code casts an abstract collection (such as a Collection, List, or Set)
to a specific concrete implementation (such as an ArrayList or HashSet).
This might not be correct, and it may make your code fragile, since
it makes it harder to switch to other concrete implementations at a future
point. Unless you have a particular reason to do so, just use the abstract
collection class.
</h5>

--------



## 391.


*  Performance - Could be refactored into a static inner class

system_tags : null, priority : 2; plugin_rule_key : SIC_INNER_SHOULD_BE_STATIC_NEEDS_THIS

<h5> This class is an inner class, but does not use its embedded reference
  to the object which created it except during construction of the
inner object.&nbsp; This reference makes the instances
  of the class larger, and may keep the reference to the creator object
  alive longer than necessary.&nbsp; If possible, the class should be
  made into a <em>static</em> inner class. Since the reference to the
   outer object is required during construction of the inner instance,
   the inner class will need to be refactored so as to
   pass a reference to the outer instance to the constructor
   for the inner class.</h5>

--------



## 392.


*  Multithreaded correctness - Incorrect lazy initialization of static field

system_tags : null, priority : 3; plugin_rule_key : LI_LAZY_INIT_STATIC

<h5> This method contains an unsynchronized lazy initialization of a non-volatile static field.
Because the compiler or processor may reorder instructions,
threads are not guaranteed to see a completely initialized object,
<em>if the method can be called by multiple threads</em>.
You can make the field volatile to correct the problem.
For more information, see the
<a href="http://www.cs.umd.edu/~pugh/java/memoryModel/">Java Memory Model web site</a>.
</h5>

--------



## 393.


*  Bad practice - Use of identifier that is a keyword in later versions of Java

system_tags : null, priority : 2; plugin_rule_key : NM_FUTURE_KEYWORD_USED_AS_IDENTIFIER

<h5>The identifier is a word that is reserved as a keyword in later versions of Java, and your code will need to be changed
in order to compile it in later versions of Java.</h5>

--------



## 394.


*  Dodgy - Result of integer multiplication cast to long

system_tags : null, priority : 3; plugin_rule_key : ICAST_INTEGER_MULTIPLY_CAST_TO_LONG

<h5>
This code performs integer multiply and then converts the result to a long,
as in:
<code>
<pre> 
	long convertDaysToMilliseconds(int days) { return 1000*3600*24*days; } 
</pre></code>
If the multiplication is done using long arithmetic, you can avoid
the possibility that the result will overflow. For example, you
could fix the above code to:
<code>
<pre> 
	long convertDaysToMilliseconds(int days) { return 1000L*3600*24*days; } 
</pre></code>
or 
<code>
<pre> 
	static final long MILLISECONDS_PER_DAY = 24L*3600*1000;
	long convertDaysToMilliseconds(int days) { return days * MILLISECONDS_PER_DAY; } 
</pre></code>
</h5>

--------



## 395.


*  Correctness - Static Thread.interrupted() method invoked on thread instance

system_tags : null, priority : 3; plugin_rule_key : STI_INTERRUPTED_ON_UNKNOWNTHREAD

<h5>
This method invokes the Thread.interrupted() method on a Thread object that appears to be a Thread object that is
not the current thread. As the interrupted() method is static, the interrupted method will be called on a different
object than the one the author intended.
</h5>

--------



## 396.


*  D'oh! A nonsensical method invocation

system_tags : null, priority : 2; plugin_rule_key : DMI_DOH

<h5>This partical method invocation doesn't make sense, for reasons that should be apparent from inspection.</h5>

--------



## 397.


*  Correctness - Self assignment of field

system_tags : null, priority : 3; plugin_rule_key : SA_FIELD_SELF_ASSIGNMENT

<h5> This method contains a self assignment of a field; e.g.
</h5>
<pre>
  int x;
  public void foo() {
    x = x;
  }
</pre>
<p>Such assignments are useless, and may indicate a logic error or typo.</p>

--------



## 398.


*  Security - Empty database password

system_tags : null, priority : 3; plugin_rule_key : DMI_EMPTY_DB_PASSWORD

<h5>This code creates a database connect using a blank or empty password. This indicates that the database is not protected by a password. 
</h5>

--------



## 399.


*  Correctness - TestCase declares a bad suite method

system_tags : null, priority : 3; plugin_rule_key : IJU_BAD_SUITE_METHOD

<h5> Class is a JUnit TestCase and defines a suite() method.
However, the suite method needs to be declared as either
<pre>public static junit.framework.Test suite()</pre>
or 
<pre>public static junit.framework.TestSuite suite()</pre>
</h5>

--------



## 400.


*  Correctness - Format string references missing argument

system_tags : null, priority : 3; plugin_rule_key : VA_FORMAT_STRING_MISSING_ARGUMENT

<h5>
Not enough arguments are passed to satisfy a placeholder in the format string.
A runtime exception will occur when 
this statement is executed.
</h5>

--------



## 401.


*  Correctness - Bitwise add of signed byte value

system_tags : null, priority : 3; plugin_rule_key : BIT_ADD_OF_SIGNED_BYTE

<h5> Adds a byte value and a value which is known to the 8 lower bits clear.
Values loaded from a byte array are sign extended to 32 bits
before any any bitwise operations are performed on the value.
Thus, if <code>b[0]</code> contains the value <code>0xff</code>, and
<code>x</code> is initially 0, then the code 
<code>((x &lt;&lt; 8) + b[0])</code>  will sign extend <code>0xff</code>
to get <code>0xffffffff</code>, and thus give the value
<code>0xffffffff</code> as the result.
</h5>

<p>In particular, the following code for packing a byte array into an int is badly wrong: </p>
<pre>
int result = 0;
for(int i = 0; i &lt; 4; i++) 
  result = ((result &lt;&lt; 8) + b[i]);
</pre>

<p>The following idiom will work instead: </p>
<pre>
int result = 0;
for(int i = 0; i &lt; 4; i++) 
  result = ((result &lt;&lt; 8) + (b[i] &amp; 0xff));
</pre>

--------



## 402.


*  Performance - Method concatenates strings using + in a loop

system_tags : null, priority : 3; plugin_rule_key : SBSC_USE_STRINGBUFFER_CONCATENATION

<h5> The method seems to be building a String using concatenation in a loop.
In each iteration, the String is converted to a StringBuffer/StringBuilder,
   appended to, and converted back to a String.
   This can lead to a cost quadratic in the number of iterations,
   as the growing string is recopied in each iteration. </h5>

<p>Better performance can be obtained by using
a StringBuffer (or StringBuilder in Java 1.5) explicitly.</p>

<p> For example:</p>
<pre>
  // This is bad
  String s = "";
  for (int i = 0; i &lt; field.length; ++i) {
    s = s + field[i];
  }

  // This is better
  StringBuffer buf = new StringBuffer();
  for (int i = 0; i &lt; field.length; ++i) {
    buf.append(field[i]);
  }
  String s = buf.toString();
</pre>

<p>
  This rule is deprecated, use {rule:squid:S1643} instead.
</p>

--------



## 403.


*  Correctness - Value annotated as carrying a type qualifier used where a value that must not carry that qualifier is required

system_tags : null, priority : 3; plugin_rule_key : TQ_ALWAYS_VALUE_USED_WHERE_NEVER_REQUIRED

<h5>
        A value specified as carrying a type qualifier annotation is
        consumed in a location or locations requiring that the value not
        carry that annotation.
        </h5>
        
        <p>
        More precisely, a value annotated with a type qualifier specifying when=ALWAYS
        is guaranteed to reach a use or uses where the same type qualifier specifies when=NEVER.
        </p>
        
        <p>
        For example, say that @NonNegative is a nickname for
        the type qualifier annotation @Negative(when=When.NEVER).
        The following code will generate this warning because
        the return statement requires a @NonNegative value,
        but receives one that is marked as @Negative.   
        </p>
        <blockquote>
<pre>
public @NonNegative Integer example(@Negative Integer value) {
    return value;
}
</pre>
        </blockquote>

--------



## 404.


*  Correctness - equals method always returns true

system_tags : null, priority : 4; plugin_rule_key : EQ_ALWAYS_TRUE

<h5> This class defines an equals method that always returns true. This is imaginative, but not very smart.
Plus, it means that the equals method is not symmetric.
</h5>

--------



## 405.


*  Bad practice - Needless instantiation of class that only supplies static methods

system_tags : null, priority : 2; plugin_rule_key : ISC_INSTANTIATE_STATIC_CLASS

<h5> This class allocates an object that is based on a class that only supplies static methods. This object
does not need to be created, just access the static methods directly using the class name as a qualifier.</h5>

--------



## 406.


*  Dodgy - Questionable cast to abstract collection

system_tags : null, priority : 2; plugin_rule_key : BC_BAD_CAST_TO_ABSTRACT_COLLECTION

<h5>
This code casts a Collection to an abstract collection
(such as <code>List</code>, <code>Set</code>, or <code>Map</code>).
Ensure that you are guaranteed that the object is of the type
you are casting to. If all you need is to be able
to iterate through a collection, you don't need to cast it to a Set or List.
</h5>

--------



## 407.


*  Bad practice - Iterator next() method can't throw NoSuchElementException

system_tags : null, priority : 1; plugin_rule_key : IT_NO_SUCH_ELEMENT

<h5> This class implements the <code>java.util.Iterator</code> interface.&nbsp;
  However, its <code>next()</code> method is not capable of throwing
  <code>java.util.NoSuchElementException</code>.&nbsp; The <code>next()</code>
  method should be changed so it throws <code>NoSuchElementException</code>
  if is called when there are no more elements to return.</h5>

--------



## 408.


*  Malicious code vulnerability - May expose internal representation by returning reference to mutable object

system_tags : null, priority : 2; plugin_rule_key : EI_EXPOSE_REP

<h5> Returning a reference to a mutable object value stored in one of the object's fields
  exposes the internal representation of the object.&nbsp;
   If instances
   are accessed by untrusted code, and unchecked changes to
   the mutable object would compromise security or other
   important properties, you will need to do something different.
  Returning a new copy of the object is better approach in many situations.</h5>

--------



## 409.


*  Multithreaded correctness - Mutable servlet field

system_tags : null, priority : 2; plugin_rule_key : MSF_MUTABLE_SERVLET_FIELD

<h5>A web server generally only creates one instance of servlet or jsp class (i.e., treats
the class as a Singleton), 
and will 
have multiple threads invoke methods on that instance to service multiple 
simultaneous requests.
Thus, having a mutable instance field generally creates race conditions.

--------



## 410.


*  Correctness - Bitwise OR of signed byte value

system_tags : null, priority : 3; plugin_rule_key : BIT_IOR_OF_SIGNED_BYTE

<h5> Loads a value from a byte array and performs a bitwise OR with
that value. Values loaded from a byte array are sign extended to 32 bits
before any any bitwise operations are performed on the value.
Thus, if <code>b[0]</code> contains the value <code>0xff</code>, and
<code>x</code> is initially 0, then the code 
<code>((x &lt;&lt; 8) | b[0])</code>  will sign extend <code>0xff</code>
to get <code>0xffffffff</code>, and thus give the value
<code>0xffffffff</code> as the result.
</h5>

<p>In particular, the following code for packing a byte array into an int is badly wrong: </p>
<pre>
int result = 0;
for(int i = 0; i &lt; 4; i++) 
  result = ((result &lt;&lt; 8) | b[i]);
</pre>

<p>The following idiom will work instead: </p>
<pre>
int result = 0;
for(int i = 0; i &lt; 4; i++) 
  result = ((result &lt;&lt; 8) | (b[i] &amp; 0xff));
</pre>

--------



## 411.


*  Multithreaded correctness - Synchronization performed on java.util.concurrent Lock

system_tags : null, priority : 3; plugin_rule_key : JLM_JSR166_LOCK_MONITORENTER

<h5> This method performs synchronization on an implementation of
<code>java.util.concurrent.locks.Lock</code>.  You should use
the <code>lock()</code> and <code>unlock()</code> methods instead.
</h5>

--------



## 412.


*  Bad practice - serialVersionUID isn't static

system_tags : null, priority : 2; plugin_rule_key : SE_NONSTATIC_SERIALVERSIONID

<h5> This class defines a <code>serialVersionUID</code> field that is not static.&nbsp;
  The field should be made static
   if it is intended to specify
   the version UID for purposes of serialization.</h5>

--------



## 413.


*  Dodgy - instanceof will always return true

system_tags : null, priority : 3; plugin_rule_key : BC_VACUOUS_INSTANCEOF

<h5>
This instanceof test will always return true (unless the value being tested is null). 
Although this is safe, make sure it isn't
an indication of some misunderstanding or some other logic error.
If you really want to test the value for being null, perhaps it would be clearer to do
better to do a null test rather than an instanceof test.
</h5>

--------



## 414.


*  Correctness - Suspicious reference comparison of Boolean values

system_tags : null, priority : 2; plugin_rule_key : RC_REF_COMPARISON_BAD_PRACTICE_BOOLEAN

This method compares two Boolean values using the == or != operator. Normally, there are only two Boolean values (Boolean.TRUE and Boolean.FALSE), but it is possible to create other Boolean objects using the new Boolean(b) constructor. It is best to avoid such objects, but if they do exist, then checking Boolean objects for equality using == or != will give results than are different than you would get using .equals(...)

--------



## 415.


*  Dodgy - Potentially dangerous use of non-short-circuit logic

system_tags : null, priority : 3; plugin_rule_key : NS_DANGEROUS_NON_SHORT_CIRCUIT

<h5> This code seems to be using non-short-circuit logic (e.g., &amp;
or |)
rather than short-circuit logic (&amp;&amp; or ||). In addition, 
it seem possible that, depending on the value of the left hand side, you might not
want to evaluate the right hand side (because it would have side effects, could cause an exception
or could be expensive.</h5>
<p>
Non-short-circuit logic causes both sides of the expression
to be evaluated even when the result can be inferred from
knowing the left-hand side. This can be less efficient and
can result in errors if the left-hand side guards cases
when evaluating the right-hand side can generate an error.
</p>

<p>See <a href="http://java.sun.com/docs/books/jls/third_edition/html/expressions.html#15.22.2">the Java
Language Specification</a> for details

</p>

--------



## 416.


*  Correctness - Impossible downcast of toArray() result

system_tags : null, priority : 4; plugin_rule_key : BC_IMPOSSIBLE_DOWNCAST_OF_TOARRAY

<h5>This code is casting the result of calling toArray() on a collection to a type more specific than Object[], as in:</h5>
<pre>
  String[] getAsArray(Collection<String> c) {
    return (String[]) c.toArray();
  }
</pre>
<p>This will usually fail by throwing a ClassCastException. The <code>toArray()</code> of almost all collections return an <code>Object[]</code>. They can't really do anything else, since the Collection object has no reference to the declared generic type of the collection.</p>
<p>The correct way to do get an array of a specific type from a collection is to use <code>c.toArray(new String[]);</code> or <code>c.toArray(new String[c.size()]);</code> (the latter is slightly more efficient).</p>
<p>There is one common/known exception exception to this. The toArray() method of lists returned by Arrays.asList(...) will return a covariantly typed array. For example, <code>Arrays.asArray(new String[] { "a" }).toArray()</code> will return a String []. FindBugs attempts to detect and suppress such cases, but may miss some.</p>

--------



## 417.


*  Malicious code vulnerability - Field should be moved out of an interface and made package protected

system_tags : null, priority : 2; plugin_rule_key : MS_OOI_PKGPROTECT

<h5>
 A final static field that is
defined in an interface references a mutable
   object such as an array or hashtable.
   This mutable object could
   be changed by malicious code or
        by accident from another package.
   To solve this, the field needs to be moved to a class
   and made package protected
   to avoid
        this vulnerability.</h5>

--------



## 418.


*  Correctness - Call to equals() comparing different types

system_tags : null, priority : 3; plugin_rule_key : EC_UNRELATED_TYPES

<h5> This method calls equals(Object) on two references of different
class types with no common subclasses.
Therefore, the objects being compared
are unlikely to be members of the same class at runtime
(unless some application classes were not analyzed, or dynamic class
loading can occur at runtime).
According to the contract of equals(),
objects of different
classes should always compare as unequal; therefore, according to the
contract defined by java.lang.Object.equals(Object),
the result of this comparison will always be false at runtime.
</h5>

--------



## 419.


*  Malicious code vulnerability - Public static method may expose internal representation by returning array

system_tags : null, priority : 3; plugin_rule_key : MS_EXPOSE_REP

<h5> A public static method returns a reference to
   an array that is part of the static state of the class.
   Any code that calls this method can freely modify
   the underlying array.
   One fix is to return a copy of the array.</h5>

--------



## 420.


*  Dodgy - Immediate dereference of the result of readLine()

system_tags : null, priority : 3; plugin_rule_key : NP_IMMEDIATE_DEREFERENCE_OF_READLINE

<h5> The result of invoking readLine() is immediately dereferenced. If there are no more lines of text
to read, readLine() will return null and dereferencing that will generate a null pointer exception.
</h5>

--------



## 421.


*  Multithreaded correctness - Empty synchronized block

system_tags : null, priority : 2; plugin_rule_key : ESync_EMPTY_SYNC

<h5> The code contains an empty synchronized block:</h5>
<pre>
synchronized() {}
</pre>
<p>Empty synchronized blocks are far more subtle and hard to use correctly
than most people recognize, and empty synchronized blocks
are almost never a better solution
than less contrived solutions.
</p>

--------



## 422.


*  Security - HTTP cookie formed from untrusted input

system_tags : null, priority : 2; plugin_rule_key : HRS_REQUEST_PARAMETER_TO_COOKIE

<h5>This code constructs an HTTP Cookie using an untrusted HTTP parameter. If this cookie is added to an HTTP response, it will allow a HTTP response splitting
vulnerability. See <a href="http://en.wikipedia.org/wiki/HTTP_response_splitting">http://en.wikipedia.org/wiki/HTTP_response_splitting</a>
for more information.</h5>
<p>FindBugs looks only for the most blatant, obvious cases of HTTP response splitting.
If FindBugs found <em>any</em>, you <em>almost certainly</em> have more 
vulnerabilities that FindBugs doesn't report. If you are concerned about HTTP response splitting, you should seriously 
consider using a commercial static analysis or pen-testing tool.
</p>

--------



## 423.


*  Correctness - Uncallable method defined in anonymous class

system_tags : null, priority : 3; plugin_rule_key : UMAC_UNCALLABLE_METHOD_OF_ANONYMOUS_CLASS

<h5> This anonymous class defined a method that is not directly invoked and does not override
a method in a superclass. Since methods in other classes cannot directly invoke methods
declared in an anonymous class, it seems that this method is uncallable. The method
might simply be dead code, but it is also possible that the method is intended to
override a method declared in a superclass, and due to an typo or other error the method does not,
in fact, override the method it is intended to.
</h5>

--------



## 424.


*  Correctness - Overwritten increment

system_tags : null, priority : 3; plugin_rule_key : DLS_OVERWRITTEN_INCREMENT

<h5>
The code performs an increment operation (e.g., <code>i++</code>) and then
immediately overwrites it. For example, <code>i = i++</code> immediately
overwrites the incremented value with the original value.
</h5>

--------



## 425.


*  Relative path traversal in servlet

system_tags : null, priority : 2; plugin_rule_key : PT_RELATIVE_PATH_TRAVERSAL

<h5>
The software uses an HTTP request parameter to construct a pathname that should be within a restricted directory,
but it does not properly neutralize sequences such as ".." that can resolve to a location that is outside of that directory.

See <a href="http://cwe.mitre.org/data/definitions/23.html">http://cwe.mitre.org/data/definitions/23.html</a> for more information.</h5>

<p>
FindBugs looks only for the most blatant, obvious cases of relative path traversal.
If FindBugs found <em>any</em>, you <em>almost certainly</em> have more
vulnerabilities that FindBugs doesn't report. If you are concerned about relative path traversal, you should seriously
consider using a commercial static analysis or pen-testing tool.
</p>

--------



## 426.


*  Performance - Method creates Boxed primitive from primitive only to get primitive value

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_BOX_TO_UNBOX

<h5>This method constructs a Boxed Primitive from a primitive only to call the primitiveValue() method to
convert it back to a primitive. Just use the primitive value instead.</h5>
<pre>
  primitive i = new BoxedPrimitive(1).primitiveValue();
    or
  primitive i = BoxedPrimitive.valueOf(1).primitiveValue();

    should just use
  primitive i = 1;
</pre>

--------



## 427.


*  Correctness - Class extends JComponent but does not implement Accessible interface

system_tags : null, priority : 0; plugin_rule_key : S508C_NON_ACCESSIBLE_JCOMPONENT

<h5>This class extends the JComponent gui control but does not implement the Accessibility interface.
This makes this control unable to be processed by screen readers, etc, for people with reading/vision
difficulties</h5>

--------



## 428.


*  Correctness - Hanging ExecutorService

system_tags : null, priority : 0; plugin_rule_key : HES_EXECUTOR_NEVER_SHUTDOWN

<h5>Most <code>ExecutorService</code> objects must be explicitly shutdown,
otherwise, their internal threads can prolong the running of the JVM, even when everything
else has stopped.</h5>

<p>FindBugs has detected that there are no calls to either the <code>shutdown()</code> or <code>shutdownNow()</code>
method, and thus, the <code>ExecutorService</code> is not guaranteed to ever terminate.  This is especially
problematic for <code>Executors.newFixedThreadPool()</code> and most of the other convenience methods in
the <code>Executors</code> class.</p>

<p>Even though there are some exceptions to this, particularly when a custom <code>ThreadFactory</code> is
provided, or for <code>ThreadPoolExecutor</code>s with <code>allowsCoreThreadTimeOut()</code> set to true,
it is good practice to explictly shutdown the <code>ExecutorService</code> when its utility is done.</p>

--------



## 429.


*  MT Correctness - Method calls Locale.setDefault()

system_tags : null, priority : 0; plugin_rule_key : MDM_SETDEFAULTLOCALE

<h5>Do not use the <code>Locale.setDefault()</code> method to change the default locale. It changes the JVM's default locale for all threads and makes your applications unsafe to threads. It does not affect the host locale. Since changing the JVM's default locale may affect many different areas of functionality, this method should only be used if the caller is prepared to reinitialize locale-sensitive code running within the same Java Virtual Machine, such as the user interface.</h5>

--------



## 430.


*  Correctness - Method performs a contravariant array assignment

system_tags : null, priority : 0; plugin_rule_key : CVAA_CONTRAVARIANT_ARRAY_ASSIGNMENT

<h5>This method contains a contravariant array assignment. Since arrays are mutable data structures, their use 
must be restricted to covariant or invariant usage</h5>

<pre>
class A {}
class B extends A {}

 B[] b = new B[2];
 A[] a = b;
</pre>

--------



## 431.


*  Style - Method uses instanceof on multiple types to arbitrate logic

system_tags : null, priority : 0; plugin_rule_key : ITC_INHERITANCE_TYPE_CHECKING

<h5>This method uses the instanceof operator in a series of if/else statements to
differentiate blocks of code based on type. If these types are related by inheritance,
it is cleaner to just define a method in the base class, and use overridden methods
in these classes.</h5>

--------



## 432.


*  Style - Method adds unrelated types to collection or array

system_tags : null, priority : 0; plugin_rule_key : UCC_UNRELATED_COLLECTION_CONTENTS

<h5>This method adds unrelated objects to a collection or array, requiring careful and brittle
data access to that collection. Create a separate class with properties needed, and add
an instance of this class to the collection or array, if possible.</h5>

--------



## 433.


*  MT Correctness - Method tests if a lock is locked

system_tags : null, priority : 0; plugin_rule_key : MDM_LOCK_ISLOCKED

<h5>Calling <code>ReentrantLock.isLocked()</code> or <code>ReentrantLock.isHeldByCurrentThread()</code> might indicate race conditions or incorrect locking. These methods are designed for use in debug code or monitoring of the system state, not for synchronization control.</h5>

--------



## 434.


*  Style - Method trims a String temporarily

system_tags : null, priority : 0; plugin_rule_key : SPP_TEMPORARY_TRIM

This method calls trim() on a String without assigning the new string to another variable.
It then calls length() or equals on this trimmed string. If trimming the string was important
for determining it's length of it's equality, it should be trimmed when you actually go to use it.
It would make more sense to first trim the String, store the trimmed value in a variable, and then
continue to test and use that trimmed string.

--------



## 435.


*  Style - Method uses old non collections interface methods

system_tags : null, priority : 0; plugin_rule_key : NCMU_NON_COLLECTION_METHOD_USE

<h5>This method makes calls to collection classes where the method is not defined by the Collections
interface, and an equivalent method exists in the interface. By using the new methods,
you can define this object by the Collections interface and allow better decoupling.</h5>

--------



## 436.


*  Correctness - Method passes a non calendar object to Calendar.before or Calendar.after

system_tags : null, priority : 0; plugin_rule_key : SPP_INVALID_CALENDAR_COMPARE

<h5>This method passes a non calendar object to the java.util.Calendar.after or java.util.Calendar.before methods.
Even though these methods take an Object as a parameter type, only Calendar type objects are supported, otherwise
false is returned</h5>

--------



## 437.


*  MT Correctness - Method sleeps without timeout

system_tags : null, priority : 0; plugin_rule_key : MDM_WAIT_WITHOUT_TIMEOUT

<h5>Calling <code>{2}</code> without timeout could block forever. Consider using a timeout to detect deadlocks or performance problems. Thread.join() Object.wait() Condition.await() Lock.lock() Lock.lockInterruptibly()</h5>

--------



## 438.


*  Performance - Method uses a ternary operator to cast a boolean to true or false

system_tags : null, priority : 0; plugin_rule_key : SPP_USELESS_TERNARY

<h5>This method tests the value of a boolean and using a ternary operator to return either true or false.
The ternary operator is completely unecessary, just use the original boolean value.</h5>

--------



## 439.


*  Style - Clone method declares it returns an type different then the owning class

system_tags : null, priority : 0; plugin_rule_key : CU_CLONE_USABILITY_MISMATCHED_RETURN

<h5>This class implements the Cloneable interface but defines its clone method to return a type
that is different than the class itself, or any interfaces that the class implements.
</h5>

--------



## 440.


*  Performance - Method copies arrays manually

system_tags : null, priority : 0; plugin_rule_key : MAC_MANUAL_ARRAY_COPY

<h5>This method copies data from one array to another manually using a loop.
It is much better performing to use System.arraycopy as this method is native.</h5>

--------



## 441.


*  Style - Method stutters exception message in logger

system_tags : null, priority : 0; plugin_rule_key : LO_STUTTERED_MESSAGE

This method uses a logger method that takes an exception, and passes the result of
the getMessage() method on the exception that occurred as the log message.
Since you are already passing in the exception, that message is already present in the
logs, and by passing it in as the message, you are just stuttering information.
It would be more helpful to provide a hand written message that describes the error in
this method, possibly including the values of key variables.

--------



## 442.


*  Correctness - Tag library is not recycleable

system_tags : null, priority : 0; plugin_rule_key : NRTL_NON_RECYCLEABLE_TAG_LIB

<h5>This Tag library class implements an attribute who's associated backing store field
is modified at another point in the tag library. In order for a taglibrary to be
recycleable, only the container is allowed to change this attribute, through the use
of the setXXX method of the taglib. By modifying the value programmatically, the
container will not initialize the attribute correctly on reuse.</h5>

--------



## 443.


*  Style - Constrained method converts checked exception to unchecked instead of another allowable checked exception

system_tags : null, priority : 0; plugin_rule_key : EXS_EXCEPTION_SOFTENING_HAS_CHECKED

<h5>This method's exception signature is constrained by an interface of super class to not throw a 
checked exception that was caught. Therefore this exception was converted to an unchecked exception and 
thrown. It would probably be better to throw the closest checked exception allowed, and to annotate
the new exception with the original exception using the initial cause field.</h5>

--------



## 444.


*  Style - Constrained method converts checked exception to unchecked

system_tags : null, priority : 0; plugin_rule_key : EXS_EXCEPTION_SOFTENING_NO_CHECKED

<h5>This method's exception signature is constrained by an interface or super class to not throw
any checked exceptions. Therefore a caught checked exception was converted to an unchecked exception
and thrown. However it appears that the class in question is owned by the same author as the constraining
interface or superclass. Consider changes the signature of this method to include the checked exception.</h5>

--------



## 445.


*  Correctness - Method uses jdbc vendor specific classes and methods

system_tags : null, priority : 0; plugin_rule_key : JVR_JDBC_VENDOR_RELIANCE

<h5>This method uses jdbc vendor specific classes and method to perform database work.
This makes the code specific to this vendor, and unable to run on other databases.</h5>

--------



## 446.


*  Performance - Method passes empty string to StringBuffer of StringBuilder constructor

system_tags : null, priority : 0; plugin_rule_key : SPP_STRINGBUFFER_WITH_EMPTY_STRING

<h5>This method calls the StringBuffer of StringBuilder constructor passing in a constant empty string ("").
This is the same as calling the default constructor, but makes the code work harder. Consider passing in a
default size instead.

--------



## 447.


*  Correctness - Method creates DOM node but doesn't attach it to a document

system_tags : null, priority : 0; plugin_rule_key : ODN_ORPHANED_DOM_NODE

<h5>This method creates a DOM node but does not attach it to a DOM document.
</h5>

--------



## 448.


*  Correctness - Comparator method doesn't seem to return all ordering values

system_tags : null, priority : 0; plugin_rule_key : SC_SUSPICIOUS_COMPARATOR_RETURN_VALUES

<h5>This compareTo or compare method returns constant values for to represent less than,
equals and greater than. However it does not return each type. Given that comparators
are transitive, this seems incorrect.</h5>

--------



## 449.


*  Correctness - Method ignores return value of a non mutating method

system_tags : null, priority : 0; plugin_rule_key : NPMC_NON_PRODUCTIVE_METHOD_CALL

<h5>This method ignores the return value of a common method that is assumed to be none mutating.
If this method does in fact not modify the object it is called on, there is no reason to call
this method, and it can be removed.

--------



## 450.


*  Style - Empty method could be declared abstract

system_tags : null, priority : 0; plugin_rule_key : ACEM_ABSTRACT_CLASS_EMPTY_METHODS

<h5>This method is empty or merely throws an exception. Since the class it is defined in is 
abstract, it may be more correct to define this method as abstract instead, so that proper
subclass behavior is enforced.</h5>

--------



## 451.


*  Correctness - Method performs algorithmic operations on the result of a toString() call

system_tags : null, priority : 0; plugin_rule_key : ITU_INAPPROPRIATE_TOSTRING_USE

<h5>This method calls algorithmic operations on a String that was returned from a toString() method.
As these methods are for debugging/logging purposes, it shouldn't be the basis of core logic in your code.

--------



## 452.


*  Correctness - Method needlessly assigns a StringBuilder to itself, as it's mutable

system_tags : null, priority : 0; plugin_rule_key : SPP_STRINGBUILDER_IS_MUTABLE

This method calls StringBuilder.append and assigns the results to the same StringBuilder as
  <pre>sb = sb.append("foo")</pre>
  As StringBuilder is mutable this is not necessary.
  This is also true of StringBuffer.

--------



## 453.


*  MT Correctness - Method attempts to manually schedule threads

system_tags : null, priority : 0; plugin_rule_key : MDM_THREAD_YIELD

<h5>Manual thread scheduling with <code>Thread.sleep()</code> or <code>Thread.yield()</code> has no guaranteed semantics and is often used to mask race conditions.</h5>

--------



## 454.


*  Performance - Method retrieves instance to load static member

system_tags : null, priority : 0; plugin_rule_key : NIR_NEEDLESS_INSTANCE_RETRIEVAL

<h5>This method calls a method to load a reference to an object, and then only
uses it to load a static member of that instance's class. It is simpler and
better performant to just load the static field from the class itself.</h5>

--------



## 455.


*  Correctness - Method attempts to store an array element to an array that does not appear to be allocated

system_tags : null, priority : 0; plugin_rule_key : AIOB_ARRAY_STORE_TO_NULL_REFERENCE

<h5>This method attempts to store an array element into an an array that appears to not have been allocated.

--------



## 456.


*  Style - Method returns different types of unrelated Objects

system_tags : null, priority : 0; plugin_rule_key : URV_UNRELATED_RETURN_VALUES

<h5>This method returns two or more unrelated types of objects (Related only through java.lang.Object).
This will be very confusing to the code that must call it.</h5>

--------



## 457.


*  Correctness - Method declares unbound method template parameter(s)

system_tags : null, priority : 0; plugin_rule_key : UMTP_UNBOUND_METHOD_TEMPLATE_PARAMETER

<h5>This method declares a method level template parameter that is not bound by any parameter of this
method. Therefore the template parameter adds no validation or type safety and can be removed, as it's
just confusing to the reader.

--------



## 458.


*  Correctness - Method concatenates the result of a toString() call

system_tags : null, priority : 0; plugin_rule_key : ISB_TOSTRING_APPENDING

<h5>This method concatenates the output of a toString() call into a StringBuffer/Builder.
It is simpler just pass the object you want to append to the to append call, as that form
does not suffer the potential for NullPointerExceptions, and is easier to read.</h5>

--------



## 459.


*  Performance - Method fetches character array just to do the equivalent of the charAt method

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_CHARAT

<h5>This method calls the toCharArray method on a String the fetch an array of characters, only
to retrieve one of those characters by index. It is more performant to just use the charAt method.
</h5>

--------



## 460.


*  Style - Method returns null for Boolean type

system_tags : null, priority : 0; plugin_rule_key : TBP_TRISTATE_BOOLEAN_PATTERN

<h5>This method declares that it returns a Boolean value. However the code
can return a null value. As this is now three values that can be returned;
Boolean.TRUE, Boolean.FALSE, null; you have changed what a Boolean means.
It would be clearer to just create a new Enum that has the three values
you want, and define that the method returns that type.</h5>

--------



## 461.


*  Performance - Method employs tail recursion

system_tags : null, priority : 0; plugin_rule_key : TR_TAIL_RECURSION

<h5>This method recursively calls itself as the last statement of the method
(Tail Recursion). This method can be easily refactored into a simple loop, which
will make it more performant, and reduce the stack size requirements.</h5>

--------



## 462.


*  Correctness - Method checks the result of a new allocation

system_tags : null, priority : 0; plugin_rule_key : UNNC_UNNECESSARY_NEW_NULL_CHECK

<h5>This method allocations an object with new, and then checks that the object is null
or non null. As the new operator is guaranteed to either succeed or throw an exception,
this null check is unnecessary and can be removed.

--------



## 463.


*  Style - Method checks the size of a collection against zero rather than using isEmpty()

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_ISEMPTY

<h5>This method calls the size() method on a collection and compares the result to zero to see if the collection
is empty. For better code clarity, it is better to just use col.isEmpty() or !col.isEmpty()</h5>

--------



## 464.


*  Performance - Method performs time consuming operation in gui thread

system_tags : null, priority : 0; plugin_rule_key : SG_SLUGGISH_GUI

<h5>This method implements an awt or swing listener and performs time 
consuming operations. Doing these operations in the gui thread will cause the
interface to appear sluggish and non-responsive to the user. Consider
using a separate thread to do the time consuming work so that the user
has a better experience.</h5>

--------



## 465.


*  Correctness - Method needlessly implements what is default streaming behavior

system_tags : null, priority : 0; plugin_rule_key : NCS_NEEDLESS_CUSTOM_SERIALIZATION

<h5>This method implements the Serializable interface by performing the same operations that
would be done if this method did not exist. Since this is the case, this method is not needed.</h5>

--------



## 466.


*  Style - Method stores return result in local before immediately returning it

system_tags : null, priority : 0; plugin_rule_key : USBR_UNNECESSARY_STORE_BEFORE_RETURN

<h5>This method stores the return result in a local variable, and then immediately
returns the local variable. It would be simpler just to return the value that is
assigned to the local variable, directly.
</h5>

--------



## 467.


*  Style - Method uses a Side Effect Constructor

system_tags : null, priority : 0; plugin_rule_key : SEC_SIDE_EFFECT_CONSTRUCTOR

<h5>This method creates an object but does not assign this object to any variable or field.
This implies that the class operates through side effects in the constructor, which is a
bad pattern to use, as it adds unnecessary coupling. Consider pulling the side effect out of
the constructor, into a separate method, or into the calling method.

--------



## 468.


*  Correctness - Circular Dependencies

system_tags : null, priority : 0; plugin_rule_key : CD_CIRCULAR_DEPENDENCY

<h5>
This class has a circular dependency with other classes. This makes building these classes
difficult, as each is dependent on the other to build correctly. Consider using interfaces
to break the hard dependency.
</h5>

--------



## 469.


*  Correctness - Method passes constant string to title/label of component

system_tags : null, priority : 0; plugin_rule_key : S508C_NON_TRANSLATABLE_STRING

<h5>This method creates a component and passes a string literal to the title or label
of the component. As this string will be shown to users, it should be internationalizable
through the use of a resource bundle.</h5>

--------



## 470.


*  Correctness - Class relies on internal api classes

system_tags : null, priority : 0; plugin_rule_key : IICU_INCORRECT_INTERNAL_CLASS_USE

<h5>This class makes use of internal api classes. As these
classes are not documented, nor externally released as part of the api, they are subject
to change or removal. You should not be using these classes.</h5>
Packages that shouldn't be used are:
<ul>
  <li>com.sun.xxx</li>
  <li>org.apache.xerces.xxx</li>
  <li>org.apache.xalan.xxx</li>
</ul>

--------



## 471.


*  Style - Method uses simple loop to copy contents of one collection to another

system_tags : null, priority : 0; plugin_rule_key : UAA_USE_ADD_ALL

<h5>This method uses a simple for loop to copy the contents of a set, list, map key/value, array or other collection
to another collection. It is simpler and more straight forward to just call the addAll method of the destination collection
passing in the source collection. In the case that the source is an array, you can use Array.asList method to massage the array
into a collection</h5>

--------



## 472.


*  Style - Method uses the same HttpRequest parameter name but with different casing

system_tags : null, priority : 0; plugin_rule_key : IKNC_INCONSISTENT_HTTP_PARAM_CASING

<h5>This method fetches an HttpServletRequest parameter with a parameter name that was used in other locations
but with a different casing. As HttpServletRequest parameters are case sensitive, this will be very confusing.

--------



## 473.


*  MT Correctness - Method calls wait, notify or notifyAll on a Thread instance

system_tags : null, priority : 0; plugin_rule_key : STS_SPURIOUS_THREAD_STATES

<h5>This method invokes the methods wait, notify or notifyAll on a Thread instance.
Doing so will confuse the internal thread state behaviour causing spurious thread
wakeups/sleeps because the internal mechanism also uses the thread instance for it's 
notifications.
</h5>

--------



## 474.


*  Correctness - Method creates promiscuous ServerSocket object

system_tags : null, priority : 0; plugin_rule_key : MDM_PROMISCUOUS_SERVERSOCKET

<h5>Do not use the <code>ServerSocket</code> constructor or <code>ServerSocketFactory.createServerSocket()</code> factory methods that accepts connections on any network interface. By default, an application that listens on a socket will listen for connection attempts on any network interface, which can be a security risk. Only the long form the <code>ServerSocket</code> constructor or <code>ServerSocketFactory.createServerSocket()</code> factory methods take a specific local address to define which network interface the socket should bind.</h5>

--------



## 475.


*  Correctness - Method attempts to log using numbered formatting anchors

system_tags : null, priority : 0; plugin_rule_key : LO_INVALID_FORMATTING_ANCHOR

This method attempts to use an SLF4J logger to log a parameterized expression using formatting anchors.
However, slf4j uses simple non numbered anchors such as {}, rather than anchors with digits in them as the 
code uses. Thus no parameter replacement will occur.

--------



## 476.


*  Style - Unconstrained method converts checked exception to unchecked

system_tags : null, priority : 0; plugin_rule_key : EXS_EXCEPTION_SOFTENING_NO_CONSTRAINTS

<h5>This method is not constrained by an interface or superclass, but converts a caught checked exception
to unchecked exception and thrown. It would be more appropriate just throw the checked exception, adding
the exception to the throws clause of the method.

--------



## 477.


*  Performance - Class defines List based fields but uses them like Sets

system_tags : null, priority : 0; plugin_rule_key : DLC_DUBIOUS_LIST_COLLECTION

<h5>This class defines a field based on java.util.List, but uses it to some extent like a Set. Since
lookup type operations are performed using a linear search for Lists, the performance for large
Lists will be poor. Consider changing this fields implementation to a set based one. If order of
iteration is important to maintain insert order, perhaps consider a LinkedHashSet.</h5>

--------



## 478.


*  Correctness - Method returns the result of invoking toString() without intermediate invocation of append() in ToStringBuilder

system_tags : null, priority : 0; plugin_rule_key : CSBTS_COMMONS_STRING_BUILDER_TOSTRING

<h5>This method returns the result of toString() on ToStringBuilder without an
intermediate invocation of append()</h5>

--------



## 479.


*  Correctness - Constructor makes call to non-final method

system_tags : null, priority : 0; plugin_rule_key : PCOA_PARTIALLY_CONSTRUCTED_OBJECT_ACCESS

<h5>This constructor makes a call to a non-final method. Since this method can be overriden, a subclasses
implementation will be executing against an object that has not been initialized at the subclass level.
You should mark all methods called from the constructor as final to avoid this problem.</h5>

--------



## 480.


*  Correctness - Method attempts to access an array element outside the array's size

system_tags : null, priority : 0; plugin_rule_key : AIOB_ARRAY_INDEX_OUT_OF_BOUNDS

<h5>This method access an array element using a literal index that is know to be outside the size of the specified
array. This will cause an ArrayIndexOutOfBoundsException at runtime</h5>

--------



## 481.


*  Correctness - Method tests a field for not null as guard and reassigns it

system_tags : null, priority : 0; plugin_rule_key : SNG_SUSPICIOUS_NULL_FIELD_GUARD

<h5>This method tests a field to make sure it's not null before executing a conditional block of
code. However in the conditional block it reassigns the field. It is likely that the guard
should have been a check to see if the field is null, not that the field was not null.</h5>

--------



## 482.


*  Correctness - Method calls wait when await was probably intended

system_tags : null, priority : 0; plugin_rule_key : SWCO_SUSPICIOUS_WAIT_ON_CONCURRENT_OBJECT

<h5>This method calls wait() on a on mutex defined in the java.util.concurrent package.
These classes, define await, instead of wait, and it is most likely that await
was intended.</h5>

--------



## 483.


*  Performance - Method appears to call the same method on the same object redundantly

system_tags : null, priority : 0; plugin_rule_key : PRMC_POSSIBLY_REDUNDANT_METHOD_CALLS

<h5>This method makes two consecutive calls to the same method using the same constant
parameters, on the same instance without any intervening changes to the objects. If this
method does not make changes to the object, which it appears it doesn't, then making
two calls is just a waste. These method calls could be combined by assigning the
result into a temporary, and using the temporary the second time.

--------



## 484.


*  Correctness - Method encodes String bytes without specifying the character encoding

system_tags : null, priority : 0; plugin_rule_key : MDM_STRING_BYTES_ENCODING

<h5>The behavior of the <code>String(byte[] bytes)</code> and <code>String.getBytes()</code> is undefined if the string cannot be encoded in the platform's default charset. Instead, use the <code>String(byte[] bytes, String encoding)</code> or <code>String.getBytes(String encoding)></code> constructor which accepts the string's encoding as an argument. Be sure to specify the encoding used for the user's locale.</h5>

--------



## 485.


*  Style - Method builds String array using String Tokenizing

system_tags : null, priority : 0; plugin_rule_key : USS_USE_STRING_SPLIT

<h5>This method uses a StringTokenizer to split up a String and then walks thru the
separated elements and builds an array from these enumerated values. It is simpler 
and easier to use the String.split method.</h5>
<p>PLEASE NOTE: String.split will return an array of 1 element when passed the 
empty string, as opposed to using StringTokenizer which returns false on the first
hasMoreElements/hasMoreTokens call. So you may need to use</p>
<pre>
  if (s.length() > 0)
    return s.split(";");
  return new String[0];
</pre>

--------



## 486.


*  Correctness - Gui uses absolute layout

system_tags : null, priority : 0; plugin_rule_key : S508C_NULL_LAYOUT

<h5>This class passes null to setLayout, which specifies that components are
to be laid out using absolute coordinates. This makes making changes for
font sizes, etc, difficult as items will not reposition
</h5>

--------



## 487.


*  Correctness - Method passes boolean expression to Assert.assertTrue

system_tags : null, priority : 0; plugin_rule_key : JAO_JUNIT_ASSERTION_ODDITIES_USE_ASSERT_EQUALS

<h5>This method evaluates a boolean expression and passes that to Assert.assertTrue. It is better 
to pass the two values that are being equated to the Assert.assertEquals method so that the
junit failure method is more meaningful of the intended test.</h5>

--------



## 488.


*  Correctness - Method passes a non array object to a parameter that expects an array

system_tags : null, priority : 0; plugin_rule_key : SPP_NON_ARRAY_PARM

This method expects an array to be passed as one of its parameters, but unfortunately defines
the parameter as Object. This invocation of this method does not pass an array and will throw
an exception when run.

--------



## 489.


*  Correctness - Method uses Properties.put instead of Properties.setProperty

system_tags : null, priority : 0; plugin_rule_key : IPU_IMPROPER_PROPERTIES_USE_SETPROPERTY

<h5>This method uses the inherited method from Hashtable put(String key, Object value) in
a Properties object. Since the Properties object was intended to be only a String to String
map, use of the derived put method is discouraged. Use the Properties.setProperty method instead.

--------



## 490.


*  Style - Method declares RuntimeException in throws clause

system_tags : null, priority : 0; plugin_rule_key : DRE_DECLARED_RUNTIME_EXCEPTION

<h5>This method declares a RuntimeException derived class in it's throws clause.
This may indicate a misunderstanding as to how unchecked exceptions are handled.
If is felt that a RuntimeException is so prevalent that it should be declared, it 
is probably a better idea to prevent the occurance in code.</h5>

--------



## 491.


*  Performance - Method uses backport concurrency utils

system_tags : null, priority : 0; plugin_rule_key : BRPI_BACKPORT_REUSE_PUBLIC_IDENTIFIERS

<h5>This class uses Backport Utils concurrent classes. Updated/Efficient version of these
classes are available in versions of the JDK 5.0 and higher, and these
classes should only be used if you are targeting JDK 1.4 and lower.
</h5>

--------



## 492.


*  Style - Method calls keySet() just to call contains, use containsKey instead

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_CONTAINSKEY

<h5>This method calls mySet.keySet().contains("foo") when mySet.containsKey("foo") is simpler</h5>

--------



## 493.


*  Correctness - Method uses reflection to call a method available on java.lang.Object

system_tags : null, priority : 0; plugin_rule_key : ROOM_REFLECTION_ON_OBJECT_METHODS

<h5>This method uses reflection to call a method that is defined in java.lang.Object.
As these methods are always available, it is not necessary to call these methods with
reflection.

--------



## 494.


*  Style - Inherited method returns more specific type of object than declared

system_tags : null, priority : 0; plugin_rule_key : URV_INHERITED_METHOD_WITH_RELATED_TYPES

<h5>This inherited method is defined to return a java.lang.Object. However, the return types returned
from this method can be defined by a more specific class or interface. If possible consider changing the
return type in the inheritance hierarchy of this method, otherwise the caller of this method will be brittle
in handling of the return type.</h5>

--------



## 495.


*  Correctness - Method explicitly sets the color of a Component

system_tags : null, priority : 0; plugin_rule_key : S508C_SET_COMP_COLOR

<h5>This method sets a Components explicitly foreground or background color which may
cause difficulty with people with vision problems from using this application.
Colors should be allowed to be set from the operating system.</h5>

--------



## 496.


*  Performance - Method assigns a variable in a larger scope then is needed

system_tags : null, priority : 0; plugin_rule_key : BAS_BLOATED_ASSIGNMENT_SCOPE

<h5><em>THIS DETECTOR IS HIGHLY EXPERIMENTAL AND IS LIKELY TO CREATE A LOT OF FUD</em>
This method assigns a value to a variable in an outer scope compared to where the variable is actually used. 
Assuming this evaluation does not have side effects, the assignment can be moved into the inner scope (if block)
so that its execution time isn't taken up if the if guard is false. Care should be
taken however that the right hand side of the assignment does not contain side 
effects that are required to happen, or that changes are not made further down that
will effect the execution of the assignment when done later on.</h5>

--------



## 497.


*  Correctness - Class defines fields that are used only as locals

system_tags : null, priority : 0; plugin_rule_key : FCBL_FIELD_COULD_BE_LOCAL

<h5>This class defines fields that are used in a locals only fashion, 
specifically private fields or protected fields in final classes that are accessed 
first in each method with a store vs. a load. This field could be replaced by one
or more local variables.</h5>

--------



## 498.


*  Style - Class uses non owned variables to synchronize on

system_tags : null, priority : 0; plugin_rule_key : NOS_NON_OWNED_SYNCHRONIZATION

<h5>This method uses a synchronize block where the object that is being synchronized on,
is not owned by this current instance. This means that other instances may use this same
object for synchronization for its own purposes causing synchronization confusion. It is 
always cleaner and safer to only synchronize on private fields of this class. Note that 'this'
is not owned by the current instance, but is owned by whomever assigns it to a field of its 
class. Synchronizing on 'this' is also not a good idea.</h5>

--------



## 499.


*  Performance - Method allocations a java.awt.Graphics object without disposing it

system_tags : null, priority : 0; plugin_rule_key : LGO_LINGERING_GRAPHICS_OBJECT

<h5>This method allocates a java.awt.Graphics object but doesn't dispose of it when done. While
the garbage collecter will clean this up, given that a large number of Graphics objects can be
created in a short period of time, it is recommended that you explicitly dispose() of them.
  </h5>

--------



## 500.


*  Correctness - Method returns an array that appears not to be initialized

system_tags : null, priority : 0; plugin_rule_key : SUA_SUSPICIOUS_UNINITIALIZED_ARRAY

<h5>This method returns an array that was allocated but apparently not initialized. It is
possible that the caller of this method will do the work of initializing this array, but
that is not a common pattern, and it is assumed that this array has just been forgotten to 
be initialized.</h5>

--------



## 501.


*  Performance - Class defines unneeded synchronization on member collection

system_tags : null, priority : 0; plugin_rule_key : NMCS_NEEDLESS_MEMBER_COLLECTION_SYNCHRONIZATION

<h5>This class defines a private collection member as synchronized. It appears however
that this collection isn't only modified in a static initializer, or constructor. As these
two areas are guaranteed to be thread safe, defining this collection as synchronized is
unnecessary and a potential performance bottleneck.</h5>

--------



## 502.


*  Correctness - Method incorrectly passes exception as first argument to logger method

system_tags : null, priority : 0; plugin_rule_key : LO_LOGGER_LOST_EXCEPTION_STACK_TRACE

<h5>This method passes an exception as the first argument to a logger method. The stack
trace is potentially lost due to the logger emitting the exception using toString(). It
is better to construct a log message with sufficient context and pass the exception as
the second argument to capture the stack trace.</h5>

--------



## 503.


*  Correctness - Method compares a double to Double.NAN

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_ISNAN

<h5>This method compares a douhle or float to the constant Double.NaN or Float.NaN. You should use
Double.isNaN(d) or Float.isNaN(f) if a primitive; or d.isNaN() or f.isNaN() if a boxed double, instead.</h5>

--------



## 504.


*  Performance - Method uses a set of collections

system_tags : null, priority : 0; plugin_rule_key : DSOC_DUBIOUS_SET_OF_COLLECTIONS

<h5>This method creates a set that contains other collections, or a Map whose keySet is
another collection. As collections tend to calculate hashCode, equals and compareTo by 
iterating the contents of the collection, this can perform poorly.</h5>
<p>In addition, when a set is used, you typically are using it to do 'contains', or 'find'
type functionality, which seems dubious when done on a collection</p>
<p>Finally, as a collection is often modified, problems will occur if the collection is 
contained in a set, because the hashCode, equals or compareTo values will change while the
collection is in the set</p>
<p>If you wish to maintain a collection of collections, it is probably better to use a List
as the outer collection</p>

--------



## 505.


*  Performance - Method converts String to primitive using excessive boxing

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_BOXING_PARSE

<h5>This method passes a String to a wrapped primitive object's valueOf method, which in turn calls
the boxedValue() method to convert to a primitive. When it is desired to convert from a String
to a primitive value, it is simpler to use the BoxedPrimitive.parseBoxedPrimitive(myString)
method. </h5>

--------



## 506.


*  Correctness - Method uses java asserts rather than a junit assertion

system_tags : null, priority : 0; plugin_rule_key : JAO_JUNIT_ASSERTION_ODDITIES_ASSERT_USED

<h5>This method uses a java assert to assure that a certain state is in effect. As this is
a junit test it makes more sense to either check this condition with a junit assert, or allow
a following exception to occur.</h5>

--------



## 507.


*  Performance - Method converts String to boxed primitive using excessive boxing

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_BOXING_VALUEOF

<h5>This method passes a String to a wrapped primitive object's parse method, which in turn calls
the valueOf() method to convert to a boxed primitive. When it is desired to convert from a String
to a boxed primitive object, it is simpler to use the BoxedPrimitive.valueOf(myString)
method. </h5>

--------



## 508.


*  Performance - Method passes constant String of length 1 to character overridden method

system_tags : null, priority : 0; plugin_rule_key : UCPM_USE_CHARACTER_PARAMETERIZED_METHOD

<h5>This method passes a constant literal String of length 1 as a parameter to a method, that
exposes a similar method that takes a character. It is simpler and more expedient to handle one
character, rather than pass a string.</h5>

--------



## 509.


*  MT Correctness - Method calls Condition.signal() rather than Condition.signalAll()

system_tags : null, priority : 0; plugin_rule_key : MDM_SIGNAL_NOT_SIGNALALL

<h5><code>Condition.signalAll()</code> is prefered over <code>Condition.signal()</code>. Calling <code>signal()</code> only wakes up one thread, meaning that the thread woken up might not be the one waiting for the condition that the caller just satisfied.</h5>

--------



## 510.


*  Correctness - Clone method stores a new value to member field of source object

system_tags : null, priority : 0; plugin_rule_key : SCA_SUSPICIOUS_CLONE_ALGORITHM

<h5>The clone method stores a value to a member field of the source object. Normally, all 
changes are made to the cloned object, and given that cloning is almost always considered
a read-only operation, this seems incorrect.</h5>

--------



## 511.


*  Performance - Method compares string without case after enforcing a case

system_tags : null, priority : 0; plugin_rule_key : SPP_USELESS_CASING

This method compares two strings with compareToIgnoreCase or equalsIgnoreCase, after having
called toUpperCase or toLowerCase on the string in question. As you are comparing with out
concern to case, the toUpperCase or toLowerCase calls are pointless and can be removed.

--------



## 512.


*  Correctness - Method deletes collection element while iterating

system_tags : null, priority : 0; plugin_rule_key : DWI_DELETING_WHILE_ITERATING

<h5>This method removes items from a collection using the remove method of the collection, while
at the same time iterating across the collection. Doing this will invalidate the iterator, and further
use of it, will cause ConcurrentModificationExceptions to be thrown. To avoid this, the remove 
method of the iterator should be used.
</h5>

--------



## 513.


*  Style - Collection Naming Confusion

system_tags : null, priority : 0; plugin_rule_key : CNC_COLLECTION_NAMING_CONFUSION

<h5>This class defines a field or local collection variable with a name that contains a different type
of collection in its name. An example woutd be a Set<User> called userList. This is confusing to the reader,
and likely caused by a previous refactor of type, without changing the name.</h5>

--------



## 514.


*  Style - Method builds xml strings through adhoc concatenation

system_tags : null, priority : 0; plugin_rule_key : CBX_CUSTOM_BUILT_XML

<h5>This method generates an xml based string by concatenating together various 
xml fragments, and variable values. Doing so makes the code difficult to read, modify 
and validate. It is much more clean to built xml structures in external files that are
read in and transformed into the final product, thru modification by Transformer.setParameter.
</h5>

--------



## 515.


*  Style - Method uses integer based for loops to iterate over a List

system_tags : null, priority : 0; plugin_rule_key : LII_LIST_INDEXED_ITERATING

<h5>This method uses an integer based for loop to iterator over a java.util.List, by calling
List.get(i) each time thru the loop. The integer is not used for other reasons. It is better
to use an Iterator instead, as depending on List implementation, iterators can perform better, 
and they also allow for exchanging of other collection types without issue.</h5>

--------



## 516.


*  Performance - Method overly synchronizes a block of code

system_tags : null, priority : 0; plugin_rule_key : BSB_BLOATED_SYNCHRONIZED_BLOCK

<h5>This methods implements a synchronized block, but the code found at the beginning
of this block  only accesses local variables, and not member variables, or this. 
To be better performance move the code that access local variables only, above the
synchronized block, and leave the synchronized block only for field accesses, or access
to this object.</h5>

--------



## 517.


*  Performance - Method passes parsed string to primitive wrapper constructor

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_BOXING_STRING_CTOR

<h5>This method passes a primitive value retrieved from a BoxedPrimitive.parseBoxedPrimitive("1") call  to 
the same class's constructor. It is simpler to just pass the string to the BoxedPrimitives constructor.
</h5>

--------



## 518.


*  Correctness - Invalid Constant Argument

system_tags : null, priority : 0; plugin_rule_key : ICA_INVALID_CONSTANT_ARGUMENT

<h5>This method passes an invalid constant value to a method parameter that expects only a select number of possible values.
This is likely going to cause this method to fail to operate correctly.</h5>

--------



## 519.


*  Correctness - Method asserts that an auto-boxed value is not null

system_tags : null, priority : 0; plugin_rule_key : JAO_JUNIT_ASSERTION_ODDITIES_IMPOSSIBLE_NULL

<h5>This method asserts that a primitive value that was autoboxed into a boxed primitive was not 
null. This will never happen, as primitives are never null, and thus the autoboxed value isn't 
either.</h5>

--------



## 520.


*  Correctness - Hanging ExecutorService

system_tags : null, priority : 0; plugin_rule_key : HES_LOCAL_EXECUTOR_SERVICE

<h5><code>ExecutorService</code>s are typically instantiated as fields so that many tasks can be executed on a controlled number of <code>Thread</code>s across many method calls.  Therefore, it is unusual for <code>ExecutorService</code>s to be a local variable, where tasks will be added only one time, in the enclosing method. </h5>

<p>Furthermore, when a local <code>ExecutorService</code> reaches the end of scope and goes up for garbage collection, the internal <code>Thread</code>s are not necessarily terminated and can prevent the JVM from ever shutting down.</p>

<p>Consider making this local variable a field and create a method that will explicitly shutdown the <code>ExecutorService</code></p>

--------



## 521.


*  Correctness - Abstract method overrides a concrete implementation

system_tags : null, priority : 0; plugin_rule_key : AOM_ABSTRACT_OVERRIDDEN_METHOD

<h5>This abstract method is derived from a concrete method implementation. It is highly
suspect that the super class method's implementation would be cast away. 
</h5>

--------



## 522.


*  Performance - Class uses an ordinary set or map with an enum class as the key

system_tags : null, priority : 0; plugin_rule_key : UEC_USE_ENUM_COLLECTIONS

<h5>This class uses an ordinary set or map collection and uses an enum class as the key type.
It is better performant to use the jdk 1.5 EnumSet or EnumMap classes.</h5>

--------



## 523.


*  Performance - Method uses iterator().next() on a List to get the first item

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_GET0

This Method calls myList.iterator().next() on a List to get the first item. It is more performant 
to just use myList.get(0).

--------



## 524.


*  Style - Method returns modified parameter

system_tags : null, priority : 0; plugin_rule_key : CFS_CONFUSING_FUNCTION_SEMANTICS

<h5>This method appears to modify a parameter, and then return this parameter as the 
methods return value. This will be confusing to callers of this method, as it won't be
apparent that the 'original' passed in parameter will be changed as well. If the purpose
of this method is to change the parameter, it would be more clear to change the method to 
a have a void return value. If a return type is required due to interface or superclass contract,
perhaps a clone of the parameter should be made.</h5>

--------



## 525.


*  Correctness - Non derivable method declares throwing an exception that isn't thrown

system_tags : null, priority : 0; plugin_rule_key : BED_BOGUS_EXCEPTION_DECLARATION

<h5>This method declares that it throws a checked exception that it does not throw. As this method is
either a constructor, static method or private method, there is no reason for this method to declare
the exception in its throws clause, and just causes calling methods to unnecessarily handle an exception
that will never be thrown. The exception in question should be removed from the throws clause.</h5>

--------



## 526.


*  Performance - Method needlessly boxes a boolean constant

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_BOOLEAN_CONSTANT_CONVERSION

<h5>This method assigns a Boxed boolean constant to a primitive boolean variable, or assigns a primitive boolean
constant to a Boxed boolean variable. Use the correct constant for the variable desired. Use</h5>
<pre>
  boolean b = true;
  boolean b = false;

  or

  Boolean b = Boolean.TRUE;
  Boolean b = Boolean.FALSE;
</pre>

--------



## 527.


*  Correctness - Method passes double value to BigDecimal Constructor

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_BIGDECIMAL_STRING_CTOR

<h5>This method calls the BigDecimal constructor that takes a double, and passes a literal double constant value. Since 
the use of BigDecimal is to get better precision than double, by passing a double, you only get the precision of double number
space. To take advantage of the BigDecimal space, pass the number as a string. </h5>

--------



## 528.


*  Correctness - Method calls equals on an enum instance

system_tags : null, priority : 0; plugin_rule_key : SPP_EQUALS_ON_ENUM

<h5>This method calls the equals(Object) method on an enum instance. Since enums values are singletons,
you can use == to safely compare two enum values. In fact, the implementation for Enum.equals does just
that.</h5>

--------



## 529.


*  Style - Method needlessly defines parameter with concrete classes

system_tags : null, priority : 0; plugin_rule_key : OCP_OVERLY_CONCRETE_PARAMETER

<h5>This method uses concrete classes for parameters when only methods defined in an implemented
interface or super class are used. Consider increasing the abstraction of the interface to
make low impact changes easier to accomplish in the future.</h5>

--------



## 530.


*  Correctness - Method calls intern on a string constant

system_tags : null, priority : 0; plugin_rule_key : SPP_INTERN_ON_CONSTANT

<h5>This method calls intern on a constant string. As constant strings are already interned, this call
is superfluous</h5>

--------



## 531.


*  Correctness - Class doesn't serialize superclass fields

system_tags : null, priority : 0; plugin_rule_key : PIS_POSSIBLE_INCOMPLETE_SERIALIZATION

<h5>This method implements Serializable but is derived from a
class that does not. The super class has fields that are not serialized
because this class does not take the responsibility of writing these fields out
either using Serializable's writeObject method, or Externalizable's writeExternal
method. Therefore when this class is read from a stream, the superclass fields
will only be initialized to the values specified in it's default constructor.
If possible, change the superclass to implement Serializable, or implement
Serializable or Externalizable methods in the child class.</h5>

--------



## 532.


*  Performance - Method allocates an object that is used in a constant way in a loop

system_tags : null, priority : 0; plugin_rule_key : PCAIL_POSSIBLE_CONSTANT_ALLOCATION_IN_LOOP

<h5>This method allocates an object using the default constructor in a loop, and then
only uses it in a quasi-static way. It is never assigned to anything that lives outside
the loop, and could potentially be allocated once outside the loop. Often this can be
achieved by calling a clear() like method in the loop, to reset the state of the object
in the loop.

--------



## 533.


*  Style - Poor Mans Enum

system_tags : null, priority : 0; plugin_rule_key : PME_POOR_MANS_ENUM

<h5>This field, although defined as a simple variable (int, String, etc) only has a set of constant values
assigned to it. Thus it appears to be used like an enum value, and should probably be defined as such.
</h5>

--------



## 534.


*  Style - Method is implemented with an exact copy of it's superclass's method

system_tags : null, priority : 0; plugin_rule_key : COM_COPIED_OVERRIDDEN_METHOD

<h5>This method is implemented using an exact copy of it's super class method's 
implementation, which usually means that this method can just be removed.
</h5>

--------



## 535.


*  Performance - Method passes simple concatenating string in StringBuffer or StringBuilder append

system_tags : null, priority : 0; plugin_rule_key : ISB_INEFFICIENT_STRING_BUFFERING

<h5>This method uses StringBuffer or StringBuilder's append method to concatenate strings. However, it passes the result
of doing a simple String concatenation to one of these append calls, thus removing any performance gains
of using the StringBuffer or StringBuilder class.</h5>

--------



## 536.


*  Style - Private method only returns one constant value

system_tags : null, priority : 0; plugin_rule_key : MRC_METHOD_RETURNS_CONSTANT

<h5>This private or static method only returns one constant value. As this method is private or static,
it's behavior can't be overridden, and thus the return of a constant value seems dubious.
Either the method should be changed to return no value, or perhaps another return value
was expected to be returned in another code path in this method.</h5>

--------



## 537.


*  Correctness - Method calls Runtime.exit() or Runtime.halt()

system_tags : null, priority : 0; plugin_rule_key : MDM_RUNTIME_EXIT_OR_HALT

<h5>Calling <code>Runtime.exit()</code> or <code>Runtime.halt()</code> shuts down the entire Java virtual machine. This should only been done when it is appropriate. Such calls make it hard or impossible for your code to be invoked by other code. Consider throwing a RuntimeException instead.</h5>

--------



## 538.


*  Correctness - Class defines static field that appears to allow memory bloat

system_tags : null, priority : 0; plugin_rule_key : PMB_POSSIBLE_MEMORY_BLOAT

<h5>This class defines static fields that are collections or StringBuffers that do not
appear to have any way to clear or reduce their size. This is a potential cause of 
memory bloat.</h5>

--------



## 539.


*  Correctness - Window sets size manually, and doesn't use pack

system_tags : null, priority : 0; plugin_rule_key : S508C_NO_SETSIZE

<h5>This class creates a window, and sizes the window using setSize. It is better
to handle font size changes to use the pack method.
</h5>

--------



## 540.


*  Style - Method asserts that a value is true or false

system_tags : null, priority : 0; plugin_rule_key : JAO_JUNIT_ASSERTION_ODDITIES_BOOLEAN_ASSERT

<h5>This method asserts that a value is equal to true or false. It is simpler to just 
use assertTrue, or assertFalse, instead.</h5>

--------



## 541.


*  Performance - Method creates Boxed primitive from primitive only to cast to another primitive type

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_BOX_TO_CAST

<h5>This method constructs a Boxed Primitive from a primitive only to call the primitiveValue() method to
cast the value to another primitive typee. It is simpler to just use casting</h5>
<pre>
  primitive i = new BoxedPrimitive(1.0).primitiveValue();
    or
  primitive i = BoxedPrimitive.valueOf(1.0).primitiveValue();

    should just use 
  primitive i = (primitive)1.0;
</pre>

--------



## 542.


*  Performance - Method concatenates an empty string to effect type conversion

system_tags : null, priority : 0; plugin_rule_key : ISB_EMPTY_STRING_APPENDING

<h5>This method concatenates an empty string with a literal value, in order to convert
the literal value into a string. It is more efficient to use String.valueOf() to do the same
thing as you do not incur the cost of creating a StringBuffer/Builder and calling methods on it
to accomplish this.</h5>

--------



## 543.


*  Performance - Method converts StringBuffer or Builder to String just to get it's length

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_STRINGBUILDER_LENGTH

<h5>This method calls the toString method on a StringBuffer or StringBuilder only to call length() on the resulting
string. It is faster, and less memory intensive to just call the length method directly on the StringBuffer or StringBuilder
itself.</h5>

--------



## 544.


*  Correctness - Method manually casts the right hand side of an assignment more specifically than needed

system_tags : null, priority : 0; plugin_rule_key : OC_OVERZEALOUS_CASTING

<h5>This method casts the right hand side of an expression to a class that is more specific than the 
variable on the left hand side of the assignment. The cast only has to be as specific as what the variable
that is on the left. Using a more specific type on the right hand side just increases cohesion.

--------



## 545.


*  Correctness - Method returns the result of invoking equals() on EqualsBuilder

system_tags : null, priority : 0; plugin_rule_key : CEBE_COMMONS_EQUALS_BUILDER_ISEQUALS

<h5>This method returns the result of equals on the EqualsBuilder type
instead of calling the method isEqual().</h5>

--------



## 546.


*  Style - Method passes an empty string to equalsIgnoreCase or compareToIgnoreCase

system_tags : null, priority : 0; plugin_rule_key : SPP_EMPTY_CASING

This method passes the empty string "" to equalsIgnoreCase or compareToIgnoreCase, as the empty string
is not case sensitive using equals is simpler. It would be even simpler to do a length() == 0 test.

--------



## 547.


*  Correctness - Method specifies an unrelated class when allocating a Logger

system_tags : null, priority : 0; plugin_rule_key : LO_SUSPECT_LOG_CLASS

<h5>This method creates a Logger by passing in a specification for a class that is unrelated
to the class in which the logger is going to be used. This is likely caused by copy/paste code.

--------



## 548.


*  Style - Method uses the same HttpSession attribute name but with different casing

system_tags : null, priority : 0; plugin_rule_key : IKNC_INCONSISTENT_HTTP_ATTRIBUTE_CASING

<h5>This method sets or gets an HttpSession attribute with a parmeter name that was used in other locations
but with a different casing. As HttpSession attribute are case sensitive, this will be very confusing.

--------



## 549.


*  Correctness - Method calls BigDecimal.equals()

system_tags : null, priority : 0; plugin_rule_key : MDM_BIGDECIMAL_EQUALS

<h5><code>equals()</code> being called to compare two <code>java.math.BigDecimal</code> numbers. This is normally a mistake, as two <code>BigDecimal</code> objects are only equal if they are equal in both value and scale, so that <i>2.0</i> is not equal to <i>2.00</i>. To compare <code>BigDecimal</code> objects for mathematical equality, use <code>compareTo()</code> instead.</h5>

--------



## 550.


*  Correctness - Method performs a contravariant array element assignment

system_tags : null, priority : 0; plugin_rule_key : CVAA_CONTRAVARIANT_ELEMENT_ASSIGNMENT

<h5>This method contains a contravariant array element assignment. Since arrays are mutable 
data structures, their use must be restricted to covariant or invariant usage</h5>

<pre>
class A {}
class B extends A {}

 B[] b = new B[2];
 A[] a = b;
 a[0] = new A(); // results in ArrayStoreException (Runtime)
</pre>

--------



## 551.


*  Correctness - Method checks a reference for null before calling instanceof

system_tags : null, priority : 0; plugin_rule_key : SPP_NULL_BEFORE_INSTANCEOF

This method checks a reference for null just before seeing if the reference is an instanceof some class.
Since instanceof will return false for null references, the null check is not needed.

--------



## 552.


*  Style - Method asserts that two doubles are exactly equal

system_tags : null, priority : 0; plugin_rule_key : JAO_JUNIT_ASSERTION_ODDITIES_INEXACT_DOUBLE

<h5>This method calls assert with two doubles or Doubles. Due to the inprecision of doubles, you
should be using the assert method that takes a range parameter that gives a range of error.</h5>

--------



## 553.


*  Correctness - Conflicting Time Units

system_tags : null, priority : 0; plugin_rule_key : CTU_CONFLICTING_TIME_UNITS

<h5>This method takes two values that appear to be representing time, and performs arithmetic operations on this
two values directly, even though it appears that the two values are representing different time units, such as
adding a millisecond value to a nanosecond value. You should convert the two values to the same time unit before
performing this calculation in order for it to be meaningful.

--------



## 554.


*  MT Correctness - Method uses suspicious thread priorities

system_tags : null, priority : 0; plugin_rule_key : MDM_THREAD_PRIORITIES

<h5>Getting or setting thread priorities is not portable and could cause or mask race conditions.</h5>

--------



## 555.


*  Performance - Method passes primitive wrapper to same primitive wrapper constructor

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_AUTOBOXING_CTOR

<h5>This method passes a wrapped primitive object to the same class's constructor.
Since wrapper classes are immutable, you can just use the original object, rather
than constructing a new one. This code works because of an abuse of autoboxing.
</h5>

--------



## 556.


*  Correctness - Serializable class defines a final transient field

system_tags : null, priority : 0; plugin_rule_key : NFF_NON_FUNCTIONAL_FIELD

<h5>This serializable class defines a field as both transient and final. As transient fields
are not serialized across the stream, it is required that some piece of code reinitialize that field
when it is deserialized. But since constructors aren't called when deserialization, the field is not initialized. 
And since the field is final, no other method can initialize it as well.</h5>

--------



## 557.


*  Correctness - Method treats null and normal strings differently than an empty strings

system_tags : null, priority : 0; plugin_rule_key : SPP_SUSPECT_STRING_TEST

<h5>This method tests a string, and groups null values with real strings, leaving empty strings as another
case. This might be perfectly valid, but normally, null strings and empty strings are logically handled the same way,
and so this test may be flawed.</h5>
<p>Pattern found is one of the following
<pre>if ((s == null) || (s.length() > 0))</pre> -- did you mean ((s == null) || (s.length() == 0))?
<pre>if ((s == null) || (s.length() != 0))</pre> -- did you mean ((s == null) || (s.length() == 0))?
<pre>if ((s != null) && (s.length() == 0))</pre> -- did you mean ((s != null) && (s.length() > 0))?
or perhaps ((s == null) || (s.length() == 0))?
</p>

--------



## 558.


*  Style - Method calls getProperties just to get one property, use getProperty instead

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_GETPROPERTY

<table>
    <tr><td>This method uses</td></tr>
    <tr><td>String prop = System.getProperties().getProperty("foo");</td></tr
    <tr><td>instead of simply using</td></tr>
    <tr><td>String prop = System.getProperty("foo");</td></tr>
  </table>

--------



## 559.


*  Performance - Method uses two date comparisons when one would do

system_tags : null, priority : 0; plugin_rule_key : DDC_DOUBLE_DATE_COMPARISON

<h5>This method compares dates with two comparisons, rather than using the reverse comparison.
So This pattern
<pre>
  if ((date1.equals( date2 )) || (date1.after( date2 )))
</pre>
could become
<pre>
  if (date1.compareTo( date2 ) >= 0)
</pre>
and
<pre>
  if ((date1.equals( date2 )) || (date1.before( date2 )))
</pre>
could become
<pre>
  if (date1.compareTo( date2 ) <= 0)
</pre>
and
<pre>
  if ((date1.before( date2 )) || (date1.after( date2 )))
</pre>
could become
<pre>
  if (!date1.equals( date2 ))
</pre>

--------



## 560.


*  Performance - Method does not presize the allocation of a collection

system_tags : null, priority : 0; plugin_rule_key : PSC_PRESIZE_COLLECTIONS

<h5>This method allocates a collection using the default constructor even though it is known
apriori how many items are going to be placed in the collection (or at least a reasonable guess)
and thus needlessly causes intermediate reallocations of the collection.
</h5>

--------



## 561.


*  Correctness - Constructor declares a Logger parameter

system_tags : null, priority : 0; plugin_rule_key : LO_SUSPECT_LOG_PARAMETER

<h5>This constructor declares a parameter that is a Logger. As loggers are meant to be
created statically per class, it doesn't make sense that you would pass a Logger from one
class to another. Declare the Logger static in each class instead.</h5>

--------



## 562.


*  Style - Method passes constant to second (actual) assertion parameter

system_tags : null, priority : 0; plugin_rule_key : JAO_JUNIT_ASSERTION_ODDITIES_ACTUAL_CONSTANT

<h5>This method calls assert passing a constant value as the second of the two values. The assert
method assumes that the expected value is the first parameter, and so it appears that the order
of values has been swapped here.</h5>

--------



## 563.


*  Correctness - Method passes a negative number as a bit to a BitSet which isn't supported

system_tags : null, priority : 0; plugin_rule_key : SPP_NEGATIVE_BITSET_ITEM

<h5>This method passes a constant negative value as a bit position to a java.util.BitSet. The BitSet class
doesn't support negative values, and thus this method call will not work as expected.</h5>

--------



## 564.


*  Correctness - Method uses array as basis of collection

system_tags : null, priority : 0; plugin_rule_key : ABC_ARRAY_BASED_COLLECTIONS

<h5>This method passes an array as the key to a Map, element in a Set, or item in a List when
the contains method is used on the List. Since arrays do not, and cannot override the equals 
method, collection inclusion is based on the reference's address, which is probably not desired.
In the case that this is a TreeMap or TreeSet, consider passing a Comparator to the map's
constructor.
</h5>

--------



## 565.


*  Style - Method stacks similar try/catch blocks

system_tags : null, priority : 0; plugin_rule_key : STB_STACKED_TRY_BLOCKS

<P>This method declares two try catch blocks one after another, where each
catch block catches the same type of exception. They also throw uniformly the
same type of exception. These two catch blocks can be combined into one to
simplify the method.</h5>

--------



## 566.


*  Correctness - Method modifies collection element while iterating

system_tags : null, priority : 0; plugin_rule_key : DWI_MODIFYING_WHILE_ITERATING

<h5>This method modifies the contents of a collection using the collection api methods, while
at the same time iterating across the collection. Doing this will invalidate the iterator, and further
use of it, will cause ConcurrentModificationExceptions to be thrown.
</h5>

--------



## 567.


*  Correctness - Method calls Array.asList on an array of primitive values

system_tags : null, priority : 0; plugin_rule_key : CAAL_CONFUSING_ARRAY_AS_LIST

<h5>This method passes an array of primitive values to the Array.asList call. As primitive
values in arrays aren't automatically promoted to boxed primitives in arrays, the asList call
cannot convert this array in a list of boxed primitives. It therefore just creates an array
with one item in it, the array itself. This is rarely what is desired.
</h5>

--------



## 568.


*  Style - Method does not define a parameter as final, but could

system_tags : null, priority : 0; plugin_rule_key : FP_FINAL_PARAMETERS

<h5>This method correctly does not write to a parameter. To help document this, and to perhaps
help the jvm optimize the invocation of this method, you should consider defining these parameters
as final.</h5>

--------



## 569.


*  Correctness - Method uses rt.jar class or method that does not exist

system_tags : null, priority : 0; plugin_rule_key : SJVU_SUSPICIOUS_JDK_VERSION_USE

<h5>This method calls a method that does not exist, on a class that does not exist in the jdk that
this class has been compiled for. This can happen if you compile the class specifying the -source and
-target options, and use a version that is before the version of the compiler's JDK.</h5>

--------



## 570.


*  Correctness - Method uses invalid C++ style null check on Boolean

system_tags : null, priority : 0; plugin_rule_key : SPP_INVALID_BOOLEAN_NULL_CHECK

<h5>This method attempts to check for null by just refering to the variable name
as would be done in C++. This ordinarily would be considered a compile error, except the
variable in question is a Boolean, which does an auto unbox to boolean.</h5>
<pre>
if (b && b.booleanValue())
should be
if ((b != null) && b.booleanValue())
</pre>

--------



## 571.


*  Correctness - Method assigns a value to a local twice in a row

system_tags : null, priority : 0; plugin_rule_key : SPP_STUTTERED_ASSIGNMENT

<h5>This method assigns a value twice in a row in a stuttered way such as
<code>a = a = 5;</code> This is most probably a cut and paste error where the duplicate
assignment can be removed.</h5>

--------



## 572.


*  Style - Method accesses statically bound class with Class.forName

system_tags : null, priority : 0; plugin_rule_key : SCR_SLOPPY_CLASS_REFLECTION

<h5>This method accesses the class object of a class that is already statically bound
in this context, with Class.forName. Using Class.forName makes reflection more fragile
in regards to code transformations such as obfuscation, and is unneeded here, since 
the class in question is already 'linked' to this class.</h5>

--------



## 573.


*  Correctness - Method returns the result of invoking hashCode() on HashCodeBuilder

system_tags : null, priority : 0; plugin_rule_key : CHTH_COMMONS_HASHCODE_BUILDER_TOHASHCODE

<h5>This method returns the result of hashCode on the HashCodeBuilder type
instead of calling the method toHashCode().</h5>

--------



## 574.


*  Correctness - Hanging ExecutorService

system_tags : null, priority : 0; plugin_rule_key : HES_EXECUTOR_OVERWRITTEN_WITHOUT_SHUTDOWN

<h5>Most <code>ExecutorService</code> objects must be explicitly shutdown, otherwise, their internal threads can prevent the JVM from ever shutting down, even when everything else has stopped.</h5>

<p>FindBugs has detected that something like the following is happening:<br/>
<code>
ExecutorService executor = ... //e.g. Executors.newCachedThreadPool();<br/>
...<br/>
public void reset() {<br/>
&nbsp;&nbsp;&nbsp;this.executor = Executors.newCachedThreadPool(); <br/>
&nbsp;&nbsp;&nbsp;this.executor.execute(new SampleExecutable()); <br/>
}<br/>
</code>
For normal objects, losing the last reference to them like this would trigger the object to be cleaned up
in garbage collection.  For <code>ExecutorService</code>s, this isn't enough to terminate the internal threads in the
thread pool, and the <code>ExecutorService</code> isn't guaranteed to shutdown, causing the JVM to never stop. <br/>
To fix this, simply add a call to <code>shutdown()</code> like this:<br/>
<code>
ExecutorService executor = ... //e.g. Executors.newCachedThreadPool();<br/>
...<br/>
public void reset() {<br/>
<b>&nbsp;&nbsp;&nbsp;this.executor.shutDown();</b> <br/>
&nbsp;&nbsp;&nbsp;this.executor = Executors.newCachedThreadPool(); <br/>
&nbsp;&nbsp;&nbsp;this.executor.execute(new SampleExecutable()); <br/>
}
</code>
</p>

<p>Even though there are some exceptions to this, particularly when a custom <code>ThreadFactory</code> is
provided, or for <code>ThreadPoolExecutor</code>s with <code>allowsCoreThreadTimeOut()</code> set to true,
it is good practice to explictly shutdown the <code>ExecutorService</code> at the end of execution, or
when it is being replaced.</p>

<p><b>Note:</b> <code>ExecutorService</code>s are generally created once in a program's lifecycle.  If you find yourself
replacing the <code>ExecutorService</code>, perhaps you may consider restructuring your code to use calls like
<code>awaitTermination()</code> or <code>Future</code>s/<code>Callable</code>s to avoid recreating the <code>ExecutorService</code>.</p>

--------



## 575.


*  Correctness - Method creates local variable-based synchronized collection

system_tags : null, priority : 0; plugin_rule_key : LSYC_LOCAL_SYNCHRONIZED_COLLECTION

<h5>This method creates a synchronized collection and store the reference to it
in a local variable. As local variables are by definition threadsafe, it seems
questionable that this collection needs to be synchronized.</h5>
<p>
<table>
  <tr><th>If you are using</th><th>consider using</th></tr>
  <tr><td>java.util.Vector</td><td>java.util.ArrayList</td></tr>
  <tr><td>java.util.Hashtable</td><td>java.util.HashMap</td></tr>
  <tr><td>java.lang.StringBuffer</td><td>java.lang.StringBuilder</td></tr>
</table>
</p>

--------



## 576.


*  Style - Method calls static method on instance reference

system_tags : null, priority : 0; plugin_rule_key : SMII_STATIC_METHOD_INSTANCE_INVOCATION

<h5>This method makes a static method call on an instance reference. For
reading comprehension of the code is better to call the method on the class,
rather than an instance. Perhaps this method's static nature has changed since
this code was written, and should be revisited.
</h5>

--------



## 577.


*  Performance - Method appends two literal strings back to back to a StringBuilder

system_tags : null, priority : 0; plugin_rule_key : SPP_DOUBLE_APPENDED_LITERALS

This method appends two literal strings to a StringBuilder back to back. This can be done with just
one append call, and may avoid intermediate reallocations of the StringBuilders backing store.

--------



## 578.


*  Performance - Method creates array using constants

system_tags : null, priority : 0; plugin_rule_key : SACM_STATIC_ARRAY_CREATED_IN_METHOD

<h5>This method creates an array initialized by constants. Each time this method is called
this array will be recreated. It would be more performant to define the array as a
static field of the class instead.</h5>

--------



## 579.


*  Style - Method makes literal string comparisons passing the literal as an argument

system_tags : null, priority : 0; plugin_rule_key : LSC_LITERAL_STRING_COMPARISON

<h5>This method calls the equals or compareTo methods on a String variable passing in a String literal.
A NullPointerException may occur if the string variable is null. If instead the method was called on
the string literal, and the variable was passed as an argument, this exception could never happen.</h5>

--------



## 580.


*  Style - Class defines two or more one for one associated lists or arrays

system_tags : null, priority : 0; plugin_rule_key : PL_PARALLEL_LISTS

<h5>This class appears to maintain two or more lists or arrays who's contains is related one-for-one
through the index of the list or array. Consider creating a separate class to hold all the related 
pieces of information, and adding instances of this class to just one list or array, or if just two values, use
a Map to associate one value with the other.</h5>

--------



## 581.


*  Correctness - Method uses same bean's getter value for setter

system_tags : null, priority : 0; plugin_rule_key : SGSU_SUSPICIOUS_GETTER_SETTER_USE

<h5>This method retrieves the property of a java bean, only to use it in the setter
for the same property of the same bean. This is usually a copy/paste typo.

--------



## 582.


*  Correctness - Equals method compares this object against other types in a non symmetric way

system_tags : null, priority : 0; plugin_rule_key : NSE_NON_SYMMETRIC_EQUALS

<h5>This class implements an equals method that compares this object against another type of object.
This is almost always a bad thing to do, but if it is to be done, you must make sure that the basic
symmetry rule of equivalence is maintained, that being if a equals b, then b equals a. It does not
appear that the class that is being compared to this class knows about this class, and doesn't compare itself
to this.</h5>

--------



## 583.


*  Correctness - Modifying Unmodifiable Collection

system_tags : null, priority : 0; plugin_rule_key : MUC_MODIFYING_UNMODIFIABLE_COLLECTION

<h5>This method attempts to modify a collection that it got from a source that could potentially have created an
immutable collection, thru Arrays.asList, Collections.unmodifiableXXX, or one of guava's methods. Doing so will cause
an exception, as these collections are not mutable.

--------



## 584.


*  Correctness - JLabel doesn't specify what it's labeling

system_tags : null, priority : 0; plugin_rule_key : S508C_NO_SETLABELFOR

<h5>This class uses JLabels that do not specify what fields are being labeled.
This hampers screen readers from given appropriate feed back to users. Use
the JLabel.setLabelFor method to accomplish this.
</h5>

--------



## 585.


*  Correctness - Method creates iterators on synchronized collections

system_tags : null, priority : 0; plugin_rule_key : SCI_SYNCHRONIZED_COLLECTION_ITERATORS

<h5>This method uses a synchronized collection, built from Collections.synchronizedXXXX, but accesses it
through an iterator. Since an iterator is by definition, multithreaded unsafe, this is a conflict in
concept. When using iterators, you should do the synchronization manually.</h5>

--------



## 586.


*  Correctness - Method puts non-String values into a Properties object

system_tags : null, priority : 0; plugin_rule_key : IPU_IMPROPER_PROPERTIES_USE

<h5>This method places non-String objects into a Properties object. As the Properties object
is intented to be a String to String map, putting non String objects is wrong, and takes advantage
of a design flaw in the Properties class by deriving from Hashtable instead of using aggregation.
If you want a collection that holds other types of objects, use a Hashtable, or better still newer collections
like HashMap or TreeMap.

--------



## 587.


*  Correctness - Method tests a local variable for not null as guard and reassigns it

system_tags : null, priority : 0; plugin_rule_key : SNG_SUSPICIOUS_NULL_LOCAL_GUARD

<h5>This method tests a local variable to make sure it's not null before executing a conditional block of
code. However in the conditional block it reassigns the local variable. It is likely that the guard
should have been a check to see if the local variable is null, not that the local variable was not null.</h5>

--------



## 588.


*  Correctness - Method accesses list or array with constant index

system_tags : null, priority : 0; plugin_rule_key : CLI_CONSTANT_LIST_INDEX

<h5>This method accesses an array or list using a constant integer index. Often,
this is a typo where a loop variable is intended to be used. If however, specific
list indices mean different specific things, then perhaps replacing the list with
a first-class object with meaningful accessors would make the code less brittle.</h5>

--------



## 589.


*  Style - Method returns more specific type of object than declared

system_tags : null, priority : 0; plugin_rule_key : URV_CHANGE_RETURN_TYPE

<h5>This method is defined to return a java.lang.Object. However, the return types
returned from this method can be defined by a more specific class or interface. Since this
method is not derived from a superclass or interface, it would be more clear to
change the return type of this method.</h5>

--------



## 590.


*  Correctness - Method defines parameters more abstractly than needed to function properly

system_tags : null, priority : 0; plugin_rule_key : PDP_POORLY_DEFINED_PARAMETER

<h5>This method defines parameters at a more abstract level than is actually needed to function correctly,
as the code casts these parameters to more concrete types. Since this method is not derivable, you should 
just define the parameters with the type that is needed.

--------



## 591.


*  Correctness - Method creates insecure Random object

system_tags : null, priority : 0; plugin_rule_key : MDM_RANDOM_SEED

<h5><code>Random()</code> constructor without a seed is insecure because it defaults to easily guessable seed: <code>System.currentTimeMillis()</code>. Initialize seed with <code>Random(SecureRandom.getInstance().generateSeed())</code> or use <code>SecureRandom</code> instead.</h5>

--------



## 592.


*  Style - Method manually creates array from collection

system_tags : null, priority : 0; plugin_rule_key : UTA_USE_TO_ARRAY

<h5>This method manually loops over a collection, pulling each element out and storing
it in an array to build an array from the collection. It is easier, and clearer to use
the built in collections method toArray. Given a collection 'mycollection' of type T, use
mycollection.toArray(new T[mycollection.size()]);

--------



## 593.


*  Correctness - Class defines methods which confuse Character with int parameters

system_tags : null, priority : 0; plugin_rule_key : CAO_CONFUSING_AUTOBOXED_OVERLOADING

<h5>This class defines two methods that differ only by a parameter being defined
as Character vs. int, long, float or double. As autoboxing is present, it may be
assumed that a parameter of 'a' would map to the Character version, but does not.</h5>

--------



## 594.


*  Performance - Method passes primitive wrapper to Wrapper class valueOf method

system_tags : null, priority : 0; plugin_rule_key : NAB_NEEDLESS_AUTOBOXING_VALUEOF

<h5>This method passes a wrapped primitive object to the same class's .valueOf method.
Since wrapper classes are immutable, you can just use the original object, rather
than calling valueOf to create a new one. This code works because of an abuse of autoboxing.
</h5>

--------



## 595.


*  Style - Unused Parameter

system_tags : null, priority : 0; plugin_rule_key : UP_UNUSED_PARAMETER

<h5>This method defines parameters that are never used. As this method is either static of private,
and can't be derived from, it is safe to remove these parameters and simplify your method.
You should consider, while unlikely, that this method may be used reflectively, and thus you will
want to change that call as well.

--------



## 596.


*  Style - Method throws exception with static message string

system_tags : null, priority : 0; plugin_rule_key : WEM_WEAK_EXCEPTION_MESSAGING

<h5>This method creates and throws an exception using a static string as the exceptions message.
Without any specific context of this particular exception invocation, such as the value of parameters, 
key member variables, or local variables, it may be difficult to infer how this exception occurred. Consider
adding context to the exception message.</h5>

--------



## 597.


*  Performance - Unjitable method

system_tags : null, priority : 0; plugin_rule_key : UJM_UNJITABLE_METHOD

<h5>This method is longer than 8000 bytes. By default the JIT will not attempt to compile this method no matter
how hot it is, and so this method will always be interpreted. If performance is important, you should consider
breaking this method up in smaller chunks. (And probably a good idea for readability too!).

--------



## 598.


*  Style - Method excessively uses methods of another class

system_tags : null, priority : 0; plugin_rule_key : CE_CLASS_ENVY

<h5><em>THIS DETECTOR IS HIGHLY EXPERIMENTAL AND IS LIKELY TO CREATE A LOT OF FUD</em></h5>
<p>This method makes extensive use of methods from another class over methods of it's own
class. Typically this means that the functionality that is accomplished by this method
most likely belongs with the class that is being used so liberally. Consider refactoring this
method to be contained in that class, and to accept all the parameters needed in the method signature.</p>

--------



## 599.


*  Correctness - Method passes an incorrect number of parameters to an SLF4J logging statement

system_tags : null, priority : 0; plugin_rule_key : LO_INCORRECT_NUMBER_OF_ANCHOR_PARAMETERS

This method passes the wrong number of parameters to a slf4j logging method (error, warn, info, debug) based on the number of anchors {} in the 
format string. An additional exception argument is allowed if found.

--------



## 600.


*  Correctness - Method calls deprecated SecureRandom method

system_tags : null, priority : 0; plugin_rule_key : MDM_SECURERANDOM

<h5>The <code>SecureRandom()</code> constructors and <code>SecureRandom.getSeed()</code> method are deprecated. Call <code>SecureRandom.getInstance()</code> and <code>SecureRandom.getInstance().generateSeed()</code> instead.</h5>

--------



## 601.


*  Style - Code calls a method passing the same value to two different arguments

system_tags : null, priority : 0; plugin_rule_key : SMA_STUTTERED_METHOD_ARGUMENTS

<h5>This method calls a method passing the same value for two or more of the parameters.
Often this is a cut/paste bug, but if not, it is confusing why you would pass the same value for two
different parameters. Perhaps an alternative method that just takes one parameter should be overridden
in this case.</h5>

--------



## 602.


*  Correctness - Method serializes an instance of a non-static inner class

system_tags : null, priority : 0; plugin_rule_key : PUS_POSSIBLE_UNSUSPECTED_SERIALIZATION

<h5>This method serializes an instance of a non-static inner class. Since this class has a
reference to the containing class, this outer class will be serialized as well. This is often
not intentional, and will make the amount of data that is serialized much more than is needed.
If the outer classes is not desired to be serialized, either make the inner class static, or
pull it out into a separate "first class" class.

--------



## 603.


*  Correctness - Method calls InetAddress.getLocalHost()

system_tags : null, priority : 0; plugin_rule_key : MDM_INETADDRESS_GETLOCALHOST

<h5>Do not call <code>InetAddress.getLocalHost()</code> on multihomed servers. On a multihomed server, <code>InetAddress.getLocalHost()</code> simply returns the IP address associated with the server's internal hostname. This could be any of the network interfaces, which could expose the machine to security risks. Server applications that need to listen on sockets should add configurable properties to define which network interfaces the server should bind.</h5>

--------



## 604.


*  Correctness - Method uses floating point indexed loops

system_tags : null, priority : 0; plugin_rule_key : FPL_FLOATING_POINT_LOOPS

<h5>This method uses floating point variables to index a loop. Since floating point
math is imprecise, rounding errors will accumulate over time each time the loop is
executed. It is usually better to use integer indexing, and calculate the new value
of the floating point number at the top of the loop body.</h5>

--------



## 605.


*  Correctness - Method uses non standard math constant

system_tags : null, priority : 0; plugin_rule_key : SPP_USE_MATH_CONSTANT

<h5>This method defines its own version of <em>PI</em> or <em>e</em> and the value is not as precise as the
one defined in the constants Math.PI or Math.E. Use these constants instead.</h5>

--------



## 606.


*  Style - Class implements interface by relying on unknowing superclass methods

system_tags : null, priority : 0; plugin_rule_key : SCII_SPOILED_CHILD_INTERFACE_IMPLEMENTOR

<h5>This class declares that it implements an interface, but does so by relying on methods supplied
by superclasses, even though those superclasses know nothing about the interface in question. If you wish
to have the child not implement all the methods of the interface, it would probably be better to declare
the superclass as implementing the interface, and if that class does not provide all the methods, then declare
that superclass abstract.</h5>

--------



## 607.


*  Correctness - Method creates and initializes a collection but never reads or gains information from it

system_tags : null, priority : 0; plugin_rule_key : WOC_WRITE_ONLY_COLLECTION_LOCAL

<h5>This method creates and initializes a collection but then never access this collection
to gain information, or fetch items from the collection. It is likely that this collection
is left over from a past effort, and can be removed.

--------



## 608.


*  Style - Class 'overloads' a method with both instance and static versions

system_tags : null, priority : 0; plugin_rule_key : MOM_MISLEADING_OVERLOAD_MODEL

<h5>This class 'overloads' the same method with both an instance and static version. As the use
of these two models is different, it will be confusing to the users of these methods.</h5>

--------



## 609.


*  Style - Class defines a serialVersionUID as non private

system_tags : null, priority : 0; plugin_rule_key : SPP_SERIALVER_SHOULD_BE_PRIVATE

This class defines a static field 'serialVersionUID' to define the serialization
version for this class. This field is marked as non private. As the serialVersionUID only
controls the current class, and doesn't effect any derived classes, defining it as non
private is confusing. It is suggested you change this variable to be private.

--------



## 610.


*  Style - Class appears to implement the old style type safe enum pattern

system_tags : null, priority : 0; plugin_rule_key : DTEP_DEPRECATED_TYPESAFE_ENUM_PATTERN

<h5>This class appears to implement the old style type safe enum pattern that was used in place of
real enums. Since this class is compiled with java 1.5 or better, it would be simpler and more 
easy to understand if it was just switched over to an enum.</h5>

--------



## 611.


*  Style - Method defines parameter list with array as last argument, rather than vararg

system_tags : null, priority : 0; plugin_rule_key : UVA_USE_VAR_ARGS

<h5>This method defines a parameter list that ends with an array. As this class is compiled with
Java 1.5 or better, this parameter could be defined as a vararg parameter instead, which can be
more convienent for client developers to use. This is not a bug, per se, just an improvement.

--------



## 612.


*  Correctness - Method has abnormal exit from finally block

system_tags : null, priority : 0; plugin_rule_key : AFBR_ABNORMAL_FINALLY_BLOCK_RETURN

<h5>This method returns or throws exceptions from a finally block. This will
mask real program logic in the try block, and short-circuit normal method termination.
</h5>

--------



## 613.


*  MT Correctness - Method ignores Lock's fairness settings by calling tryLock()

system_tags : null, priority : 0; plugin_rule_key : MDM_THREAD_FAIRNESS

<h5>Calling <code>Lock.tryLock()</code> or <code>ReentrantLock.tryLock()</code> without a timeout does not honor the lock's fairness setting. If you want to honor the fairness setting for this lock, then use <code>tryLock(0, TimeUnit.SECONDS)</code> which is almost equivalent (it also detects interruption).</h5>

--------



## 614.


*  Correctness - Class creates and initializes a collection but never reads or gains information from it

system_tags : null, priority : 0; plugin_rule_key : WOC_WRITE_ONLY_COLLECTION_FIELD

<h5>This class creates and initializes a collection as a field but then never access this collection
to gain information, or fetch items from the collection. It is likely that this collection
is left over from a past effort, and can be removed.

--------



## 615.


*  Correctness - Method passes appended string to title/label of component

system_tags : null, priority : 0; plugin_rule_key : S508C_APPENDED_STRING

<h5>This method creates a component and passes a string that was build up from a number of
strings through appending multiple strings together. As foreign languages may order phrases
differently, this will make translations difficult.</h5>

--------



## 616.


*  Correctness - Method compares class name instead of comparing class

system_tags : null, priority : 0; plugin_rule_key : CCNE_COMPARE_CLASS_EQUALS_NAME

<h5>In a JVM, Two classes are the same class (and consequently the same type) if
they are loaded by the same class loader, and they have the same fully
qualified name [JVMSpec 1999].

Comparing class name ignores the class loader.
</h5>

--------



## 617.


*  Correctness - Method modifies http session attribute without calling setAttribute

system_tags : null, priority : 0; plugin_rule_key : SCSS_SUSPICIOUS_CLUSTERED_SESSION_SUPPORT

<h5>This method fetches a complex object from an HttpSession object, modifies this object, but does
not call setAttribute, to inform the application server that this attribute has been changed. This will
cause this attribute not to be updated in other servers in a clustered environment, as only changes marked
by a call to setAttribute are replicated.</h5>

--------



## 618.


*  Style - Clone method declares it throws CloneNotSupportedException

system_tags : null, priority : 0; plugin_rule_key : CU_CLONE_USABILITY_THROWS

<h5>This class implements the Cloneable interface but defines its clone method to still return
a CloneNotSupportedException. Since you are implementing clone() it would make sense that the method
in question will <em>not</em> throw that exception, so annotating your method with it just makes client use
of your more painful as they have to handle an exception that will never happen. Just remove the
throws clause from your method.
</h5>

--------



## 619.


*  Correctness - Method throws alternative exception from catch block without history

system_tags : null, priority : 0; plugin_rule_key : LEST_LOST_EXCEPTION_STACK_TRACE

<h5>This method catches an exception, and throws a different exception, without incorporating the
original exception. Doing so hides the original source of the exception making debugging and fixing
these problems difficult. It is better to use the constructor of this new exception that takes an
original exception so that this detail can be passed along to the user.</h5>

--------



## 620.


*  Style - Method uses 1 element array to simulate call by reference

system_tags : null, priority : 0; plugin_rule_key : AWCBR_ARRAY_WRAPPED_CALL_BY_REFERENCE

<h5>This method uses a one element array to wrap an object that is to be passed to a method as an argument
to simulate call by pointer ala C++. It is better to define a proper return class type that holds all
the relevant information retrieved from the called method.</h5>

--------



## 621.


*  Style - Clone method declares it returns an Object

system_tags : null, priority : 0; plugin_rule_key : CU_CLONE_USABILITY_OBJECT_RETURN

<h5>This class implements the Cloneable interface but defines its clone method to return an
Object. Since most likely users of this method will need to cast it to the real type, this will
be more painful than necessary. Just declare the return value to be the type of this class.
</h5>

--------



## 622.


*  Correctness - Method appears to pass character to StringBuffer or StringBuilder integer constructor

system_tags : null, priority : 0; plugin_rule_key : SPP_NO_CHAR_SB_CTOR

<h5>This method constructs a StringBuffer or a StringBuilder using the constructor that takes an integer, but
appears to pass a character instead. It is probable that the author assumed that character would be appended to the
StringBuffer/Builder, but instead the integer value of the character is used as an initial size for the buffer.
</h5>

--------



## 623.


*  Performance - Method executes sql queries inside of loops

system_tags : null, priority : 0; plugin_rule_key : SIL_SQL_IN_LOOP

<h5>This method executes sql queries inside of a loop. This pattern is often inefficient
as the number of queries may mushroom in fencepost cases. It is probably more performant
to loop over the input and collect the key data needed for the query for all items, and
issue one query using an in clause, or similar construct, and then loop over this result
set, and fetch all the data at once.</h5>

--------



## 624.


*  Correctness - Method triggers finalization

system_tags : null, priority : 0; plugin_rule_key : MDM_RUNFINALIZATION

<h5>Manually triggering finalization can result in serious performance problems and may be masking resource cleanup bugs.</h5>

--------



## 625.


*  Useless parentheses around expressions should be removed to prevent any misunderstanding

system_tags : null, priority : 2; plugin_rule_key : UselessParenthesesCheck

<h5>
Useless parentheses can sometimes be misleading and so should be removed.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
return 3;             // Compliant
return (x);           // Non-Compliant
return (x + 1);       // Non-Compliant
int x = (y / 2 + 1);  // Non-Compliant
int y = (4+X) * y;    // Compliant
</pre>

--------



## 626.


*  Methods should not have too many lines

system_tags : brain-overload, priority : 2; plugin_rule_key : S138

<h5>
A method that grows too large tends to aggregate too many responsibilities.
Such methods inevitably become harder to understand and therefore harder to maintain.
</h5>

<p>
Above a specific threshold, it is strongly advised to refactor into smaller methods which focus on well-defined tasks.
Those smaller methods will not only be easier to understand, but also probably easier to test.
</p>

--------



## 627.


*  The Array.equals(Object obj) method should never be used

system_tags : convention, priority : 3; plugin_rule_key : S1294

<h5>Since arrays do not override <code>Object.equals()</code>, calling equals on two arrays is the same as comparing their addresses. This means that <code>array1.equals(array2)</code> is equivalent to <code>array1==array2</code>.</h5>

<p>However, some developers might expect Array.equals(Object obj) to do more than a simple memory address comparison, comparing for instance the size and content of the two arrays. To prevent such a misunderstanding, the '==' operator or <code>Arrays.equals(array1, array2)</code> must always be used in place of the Array.equals(Object obj) method.</p>

<h2>Noncompliant Code Example</h2>
<pre>
String[] array1 = ...
String[] array2 = ...
...
if(array1.equals(array2)){
...
}
</pre>

<h2>Compliant</h2>
<pre>
String[] array1 = ...
String[] array2 = ...
...
if(array1 == array2){
...
}
//or
if(Arrays.equals(array1, array2)) {
  ...
}
</pre>

<h2>See</h2>

<table class="data">
  <thead>
    <tr><th>Tool</th>
    <th>Reference</th>
    <th>Description</th></tr>
  </thead>
  <tbody>
  <tr>
    <td>Findbugs</td>
    <td>EC_INCOMPATIBLE_ARRAY_COMPARE</td>
    <td>Correctness - equals(...) used to compare incompatible arrays</td>
  </tr>
  <tr>
    <td>Findbugs</td>
    <td>EC_BAD_ARRAY_COMPARE</td>
    <td>Correctness - Invocation of equals() on an array, which is equivalent to ==</td>
  </tr>
  </tbody>
</table>

--------



## 628.


*  Loops should not contain more than a single "break" or "continue" statement

system_tags : brain-overload, priority : 2; plugin_rule_key : S135

<h5>Restricting the number of <code>break</code> and <code>continue</code> statements in a loop is done in the interest of good structured programming.</h5>

<p>
One <code>break</code> and <code>continue</code> statement is acceptable in a loop, since it facilitates optimal coding. If there is more than one, the code should be refactored to increase readability.
</p>

<p>The following code:</p>

<h2>Noncompliant Code Example</h2>

<pre>
for (int i = 1; i <= 10; i++) {     // Noncompliant - 2 continue - one might be tempted to add some logic in between
  if (i % 2 == 0) {
    continue;
  }

  if (i % 3 == 0) {
    continue;
  }

  System.out.println("i = " + i);
}
</pre>

--------



## 629.


*  Enumeration should not be implemented

system_tags : null, priority : 2; plugin_rule_key : S1150

<h5>From the official Oracle Javadoc:</h5>

<blockquote>
NOTE: The functionality of this Enumeration interface is duplicated by the Iterator interface.
In addition, Iterator adds an optional remove operation, and has shorter method names.
New implementations should consider using Iterator in preference to Enumeration.
</blockquote>

<p>The following code:</p>

<pre>
public class MyClass implements Enumeration {  // Non-Compliant
  /* ... */
}
</pre>

<p>should be refactored into:</p>

<pre>
public class MyClass implements Iterator {     // Compliant
  /* ... */
}
</pre>

--------



## 630.


*  Switch cases should not have too many lines

system_tags : brain-overload, priority : 2; plugin_rule_key : S1151

<h5>Switch cases should remain small to keep the overall switch compact and readable.</h5>

<p>The following code snippet illustrates this rule with the default threshold of 5:</p>

<pre>
switch (myVariable) {
  case 0:                     // Compliant - 5 lines till following case
    System.out.println("");
    System.out.println("");
    System.out.println("");
    break;
  default:                    // Non-Compliant - 6 lines till switch end
    System.out.println("");
    System.out.println("");
    System.out.println("");
    System.out.println("");
    break;
}
</pre>

--------



## 631.


*  Member variable visibility should be specified

system_tags : security, priority : 2; plugin_rule_key : S2039

<h5>Failing to explicitly declare the visibility of a member variable could result it in having a visibility you don't expect, and potentially leave it open to unexpected modification by other classes.</h5>

<h2>Noncompliant Code Sample</h2>
<pre>
class Ball {
  String color="red";  // Noncompliant
}
enum A {
 B;
 int a;
}
</pre>

<h2>Compliant Solution</h2>
<pre>
class Ball {
  private String color="red";  // Compliant
}
enum A {
 B;
 private int a;
}
</pre>

--------



## 632.


*  Avoid use of //NOSONAR marker

system_tags : null, priority : 0; plugin_rule_key : NoSonar

<h5>Any issue to quality rule can be deactivated with the
	//NOSONAR marker. This marker is pretty useful to exclude
	false-positive results but sometimes it can abusively be used to hide
	real quality flaws.</h5>
<p>This rule allows to track and/or forbid use of this marker</p>

--------



## 633.


*  Classes and methods that rely on the default system encoding should not be used

system_tags : bug, priority : 2; plugin_rule_key : S1943

<h5>Using classes and methods that rely on the default system encoding can result in code that works fine in its "home" environment. But that code may break for customers who use different encodings in ways that are extremely difficult to diagnose and nearly, if not completely, impossible to reproduce when it's time to fix them.</h5>

<p>This rule detects uses of the following classes and methods:</p>
<ul>
	<li><code>FileReader</code></li>
	<li><code>FileWriter</code></li>
	<li>String constructors with a <code>byte[]</code> argument but no <code>Charset</code> argument
		<ul>
			<li><code>String(byte[] bytes)</code></li>
			<li><code>String(byte[] bytes, int offset, int length)</code> </li>
		</ul>
	</li>
<li><code>String.getBytes()</code></li>
<li><code>String.getBytes(int srcBegin, int srcEnd, byte[] dst, int dstBegin)</code></li>
<li><code>InputStreamReader(InputStream in)</code></li>
<li><code>OutputStreamWriter(OutputStream out)</code></li>
<li><code>ByteArrayOutputStream.toString()</code></li>
<li>Some <code>Formatter</code> constructors
	<ul>
		<li><code>Formatter(String fileName)</code></li>
		<li><code>Formatter(File file)</code></li>
		<li><code>Formatter(OutputStream os)</code></li>
	</ul>
</li>
<li>Some <code>Scanner</code> constructors
	<ul>
		<li><code>Scanner(File source)</code></li>
		<li><code>Scanner(Path source)</code></li>
		<li><code>Scanner(InputStream source)</code></li>
	</ul>
</li>
<li>Some <code>PrintStream</code> constructors
	<ul>
		<li><code>PrintStream(File file)</code></li>
		<li><code>PrintStream(OutputStream out)</code></li>
		<li><code>PrintStream(OutputStream out, boolean autoFlush)</code></li>
		<li><code>PrintStream(String fileName)</code></li>
	</ul>
</li>
<li>Some <code>PrintWriter</code> constructors
	<ul>
		<li><code>PrintWriter(File file)</code></li>
		<li><code>PrintWriter(OutputStream out)</code></li>
		<li><code>PrintWriter(OutputStream out, boolean autoFlush)</code></li>
		<li><code>PrintWriter(String fileName)</code></li>
	</ul>
</li>
</ul>

--------



## 634.


*  "ResultSet.isLast()" should not be used

system_tags : performance,pitfall, priority : 3; plugin_rule_key : S2232

<h5>There are several reasons to avoid <code>ResultSet.isLast()</code>. First, support for this method is optional for <code>TYPE_FORWARD_ONLY</code> result sets. Second, it can be expensive (the driver may need to fetch the next row to answer the question). Finally, the specification is not clear on what should be returned when the <code>ResultSet</code> is empty, so some drivers may return the opposite of what is expected.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
stmt.executeQuery("SELECT name, address FROM PERSON");
ResultSet rs = stmt.getResultSet();
while (! rs.isLast()) { // Noncompliant
// process row
}
</pre>

<h2>Compliant Solution</h2>
<pre>
ResultSet rs = stmt.executeQuery("SELECT name, address FROM PERSON");
while (! rs.next()) {
// process row
}
</pre>

--------



## 635.


*  Primitive wrappers should not be instantiated only to perform a to String conversion

system_tags : null, priority : 2; plugin_rule_key : S1158

<h5>
Creating temporary primitive wrapper objects only for <code>String</code> conversion is inefficient.
Instead, the static <code>toString()</code> method of those primitive wrapper classes should be used.
</h5>

<p>For example, the following code:</p>

<pre>
new Integer(myInteger).toString();  // Non-Compliant
</pre>

<p>should be refactored into:</p>

<pre>
Integer.toString(myInteger);      // Compliant
</pre>

--------



## 636.


*  Case insensitive string comparisons should be made without intermediate upper or lower casing

system_tags : null, priority : 2; plugin_rule_key : S1157

<h5>
Using <code>toLowerCase()</code> or <code>toUpperCase()</code> to make case insensitive comparisons is inefficient because it requires the creation of temporary, intermediate <code>String</code> objects.
</h5>

<p>The following code:</p>

<pre>
boolean result1 = foo.toUpperCase().equals(bar);             // Non-Compliant
boolean result2 = foo.equals(bar.toUpperCase());             // Non-Compliant
boolean result3 = foo.toLowerCase().equals(bar.LowerCase()); // Non-Compliant
</pre>

<p>should be refactored into:</p>

<pre>
boolean result = foo.equalsIgnoreCase(bar);                  // Compliant
</pre>

--------



## 637.


*  Non-public methods should not be "@Transactional"

system_tags : bug,spring, priority : 3; plugin_rule_key : S2230

Marking a non-public method <code>@Transactional</code> is both useless and misleading because Spring doesn't "see" non-<code>public</code> methods, and so makes no provision for their proper invocation. Nor does Spring make provision for the methods invoked by the method it called.

Therefore marking a <code>private</code>  method, for instance, <code>@Transactional</code> can only result in a runtime error or exception if the method is actually written to be <code>@Transactional</code>.

<h2>Noncompliant Code Example</h2>
<pre>
@Transactional  // Noncompliant
private void doTheThing(ArgClass arg) {
  // ...
}
</pre>

--------



## 638.


*  Collection.isEmpty() should be used to test for emptiness

system_tags : null, priority : 2; plugin_rule_key : S1155

<h5>
Using <code>Collection.size()</code> to test for emptiness works, but using <code>Collection.isEmpty()</code> makes the code more readable and can be more performant. The time complexity of any <code>isEmpty()</code> method implementation should be <code>O(1)</code> whereas some implementations of <code>size()</code> method can be <code>O(n)</code>.

</h5>

<h2>Noncompliant Code Example</h2>

<pre>
if (myCollection.size() == 0) {  // Non-Compliant
  /* ... */
}
</pre>

<h2>Compliant Solution</h2>

<pre>
if (myCollection.isEmpty()) {    // Compliant
  /* ... */
}
</pre>

--------



## 639.


*  Methods "wait(...)", "notify()" or "notifyAll()" should never be called on Thread instances

system_tags : bug,multi-threading, priority : 3; plugin_rule_key : S2236

<h5>On a Thread instance, methods <code>wait(...)</code>, <code>notify()</code> and <code>notifyAll()</code> are available only because all classes in Java extends <code>Object</code> and therefore automatically inherit the methods. But there are two very good reasons to not call those methods on a Thread instance :</h5>
<ul>
  <li>Doing so is really confusing. What is really expected when calling, for instance, the <code>wait(...)</code> method on a Thread ? That the execution of the Thread is suspended, or that acquisition of the object monitor is waited for ?</li>
  <li>Internally, the JVM relies on those method calls to change the state of the Thread (<code>BLOCKED</code>, <code>WAITING</code>, ...), so calling them will corrupt the behavior of the JVM</li>
  </ul>

<h2>Noncompliant Code Example</h2>

<pre>
Thread myThread = new Thread(new RunnableJob());
...
myThread.wait(2000);
</pre>

--------



## 640.


*  Fields in a "Serializable" class should either be transient or serializable

system_tags : bug,cwe, priority : 2; plugin_rule_key : S1948

<h5>Fields in a <code>Serializable</code> class must themselves be either <code>Serializable</code> or <code>transient</code> even if the class is never explicitly serialized or deserialized. That's because under load, most J2EE application frameworks flush objects to disk, and an allegedly <code>Serializable</code> object with non-transient, non-serializable data members could cause program crashes, and open the door to attackers.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public class Address {
  //...
}

public class Person implements Serializable {
  private static final long serialVersionUID = 1905122041950251207L;

  private String name;
  private Address address;  // Noncompliant; Address isn't serializable
}
</pre>

<h2>Compliant Example</h2>
<pre>
public class Address implements Serializable {
  private static final long serialVersionUID = 2405172041950251807L;
}

public class Person implements Serializable {
  private static final long serialVersionUID = 1905122041950251207L;

  private String name;
  private Address address;
}
</pre>

<h2>Exceptions</h2>
<p>The alternative to making all members <code>serializable</code> or <code>transient</code> is to implement special methods which take on the responsibility of properly serializing and de-serializing the object. This rule ignores classes which implement the following methods:</p>

<pre>
private void writeObject(java.io.ObjectOutputStream out) throws IOException
private void readObject(java.io.ObjectInputStream in) throws IOException, ClassNotFoundException;
</pre>

<h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/594.html">MITRE, CWE-594</a> - Saving Unserializable Objects to Disk</li>
      <li><a href="http://docs.oracle.com/javase/6/docs/api/java/io/Serializable.html">Oracle Java 6, Serializable</a></li>
      <li><a href="http://docs.oracle.com/javase/7/docs/api/java/io/Serializable.html">Oracle Java 7, Serializable</a></li>
    </ul>

--------



## 641.


*  String.valueOf() should not be appended to a String

system_tags : null, priority : 1; plugin_rule_key : S1153

<h5>
Appending <code>String.valueOf()</code> to a <code>String</code> decreases the code readability.
The argument passed to <code>String.valueOf()</code> should be directly appended instead.
</h5>

<p>The following code:</p>

<pre>
public void display(int i){
  System.out.println("Output is " + String.valueOf(i));    // Non-Compliant
}
</pre>

<p>should be refactored into:</p>

<pre>
public void display(int i){
  System.out.println("Output is " + i);                    // Compliant
}
</pre>

--------



## 642.


*  IllegalMonitorStateException should never be caught

system_tags : bug,multi-threading, priority : 3; plugin_rule_key : S2235

According to Oracle Javadoc:
<blockquote>
<code>IllegalMonitorStateException</code> is thrown when a thread has attempted to wait on an object's monitor or to notify other threads waiting on an object's monitor without owning the specified monitor.
</blockquote>

In other words, this exception can be thrown only in case of bad design because <code>Object.wait(...)</code>, <code>Object.notify()</code> and <code>Object.notifyAll()</code> methods should never be called on an object whose monitor is not held. 

<h2>Noncompliant Code Example</h2>
<pre>
public void doSomething(){
  ...
  try {
    ...
    anObject.notify();
    ...
  } catch(IllegalMonitorStateException e) {
    ...
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public void doSomething(){
  ...
  synchronized(anObject) {
    ...
    anObject.notify();
    ...
  }
}
</pre>

--------



## 643.


*  Identical expressions should not be used on both sides of a binary operator

system_tags : cert, priority : 2; plugin_rule_key : S1764

<h5>Using the same value on either side of a binary operator is almost always a mistake. In the case of logical operators, it is simply wasted code, and should be simplified. In the case of bitwise operators and most binary mathematical operators, it yields predictable results, and should be simplified.</h5>

<p>This rule ignores <code>*</code>, <code>+</code> and <code>-</code>.</p>

<h2>Noncompliant Code Example</h2>
<pre>
if ( a == a ) { // always true
  doZ();
}
if ( a != a ) { // always false
  doY();
}
if ( a == b && a == b ) { // if the first one is true, the second one is too
  doX();
}
if ( a == b || a == b ) { // if the first one is true, the second one is too
  doW();
}

int j = 5 / 5; //always 1
int k = 5 - 5; //always 0
</pre>

<h2>Compliant Solution</h2>
<pre>
doZ();

if ( a == b ) {
  doX();
}
if ( a == b ) {
  doW();
}
int j = 1;
int k = 0;

</pre>

<h2>Exceptions</h2>
<p>The specific case of testing a floating point values against itself is a valid test for NaN and is therefore ignored.</p>
<p>Similarly, left-shifting 1 onto 1 is common in the construction of bit masks, and is ignored.</p>
<pre>
  float f;
  double d;
  if(f !=f || d != d) { //test for NaN value
    System.out.println("f or d is NaN");
  } else if ( f != d) { //Noncomliant
    //...
  }
  int i = 1 << 1; //Compliant
  int j = a << a; //Noncompliant
</pre>

<h2>See</h2>
    <ul>
      <li><a href="https://www.securecoding.cert.org/confluence/x/NYA5">CERT, MSC12-C</a> - Detect and remove code that has no effect</li>
      <li><a href="https://www.securecoding.cert.org/confluence/x/SIIyAQ">CERT, MSC12-CPP</a> - Detect and remove code that has no effect</li>
      <li>{rule:squid:S1656} - Implements a check on =.</li>
    </ul>

--------



## 644.


*  Public types, methods and fields (API) should be documented with Javadoc

system_tags : convention, priority : 2; plugin_rule_key : UndocumentedApi

<h5>
Try to imagine using the standard Java API (Collections, JDBC, IO, ...) without Javadoc.
It would be a nightmare, because Javadoc is the only way to understand of the contract of the API.
Documenting API with Javadoc increases the productivity of the developers consuming it.
</h5>

<p>The following Javadoc elements are required:</p>
<ul>
  <li>Parameters, using <code>@param parameterName</code>.</li>
  <li>Method return values, using <code>@return</code>.</li>
  <li>Generic types, using <code>@param &lt;T&gt;</code>.</li>
</ul>

<p>The following public methods and constructors are not taken into account by this rule:</p>
<ul>
  <li>Getters and setters.</li>
  <li>Methods with @Override annotation.</li>
  <li>Empty constructors.</li>
  <li>Static constants.</li>
</ul>

<p>The following code snippet illustrates this rule:</p>

<pre>
/**
  * This is a Javadoc comment
  */
public class MyClass&lt;T&gt; implements Runnable {    // Non-Compliant - missing '@param &lt;T&gt;'

  public static final DEFAULT_STATUS = 0;        // Compliant - static constant
  private int status;                            // Compliant - not public

  /**
    * This is a Javadoc comment
    */
  public String message;                         // Compliant - well documented

  public MyClass() {                             // Non-Compliant - missing documentation
    this.status = DEFAULT_STATUS;
  }

  public void setStatus(int status) {            // Compliant - setter
    this.status = status;
  }

  @Override
  public void run() {                            // Compliant - has @Override annotation
  }

  protected void doSomething() {                 // Compliant - not public
  }

  /**
    * @param value ...
    */
  public void doSomething(int value) {           // Compliant
  }

  /**
    */
  public int doSomething(int value) {            // Non-Compliant - missing '@param value' and '@return'
    return value;
  }
}
</pre>

--------



## 645.


*  Comments should not be located at the end of lines of code

system_tags : convention, priority : 1; plugin_rule_key : TrailingCommentCheck

<h5>
This rule verifies that single-line comments are not located at the end of a line of code.
The main idea behind this rule is that in order to be really readable, trailing comments would have to be property written and formatted (correct alignment, no interference with the visual structure of the code, not too long to be visible) but most often, automatic code formatters would not handle this correctly: the code would end up less readable.
Comments are far better placed on the previous empty line
of code, where they will always be visible and properly formatted.
</h5>

<p>
However, this rule allows to write trailing "metadata comments" - for which the pattern is configurable, as those metadata comments are usually very short and heavily used in some cases.
</p>

<pre>
// The following line is non-compliant
int a1 = b + c; // This is a trailing comment that can be very very long

// This very long comment is better placed before the line of code
int a2 = b + c;

// The following line is compliant with the default configuration of the rule
String a3 = "id"; // $NON-NLS-1$
</pre>

--------



## 646.


*  Avoid too deep inheritance tree

system_tags : null, priority : 2; plugin_rule_key : MaximumInheritanceDepth

<h5>Inheritance is certainly one of the most valuable concept of
	object-oriented programming. It's a way to compartmentalize and reuse
	code by creating collections of attributes and behaviors called classes
	which can be based on previously created classes. But abusing of this
	concept by creating a deep inheritance tree can lead to very complex
	and unmaintainable source code.</h5>
<p>Most of the time a too deep inheritance tree is due to bad object
	oriented design which has led to systematically use 'inheritance' when
	'composition' would suit better.</p>

--------



## 647.


*  Constructors should only call non-overridable methods

system_tags : bug, priority : 2; plugin_rule_key : S1699

<h5>Calling an overridable method from a constructor could result in failures or strange behaviors when instantiating a subclass which overrides the method.</h5>

<p>For example:
<ul>
<li>The subclass class constructor starts by contract by calling the parent class constructor.</li>
<li>The parent class constructor calls the method, which has been overridden in the child class.</li>
<li>If the behavior of the child class method depends on fields that are initialized in the child class constructor, unexpected behavior (like a <code>NullPointerException</code>) can result, because the fields aren't initialized yet.</li>
</p>

<h2>Noncompliant Code Example</h2>
<pre>
public class Parent {

  public Parent () {
    doSomething();  // Noncompliant
  }

  public void doSomething () {  // not final; can be overridden
    ...
  }
}

public class Child extends Parent {

  private String foo;

  public Parent(String foo) {
    super(); // leads to call doSomething() in Parent constructor which triggers a NullPointerException as foo has not yet been initialized
    this.foo = foo;
  }

  public void doSomething () {
    System.out.println(this.foo.length());
  }

}
</pre>

--------



## 648.


*  Switch cases should end with an unconditional break statement

system_tags : pitfall, priority : 3; plugin_rule_key : S128

<h5>
When the execution is not explicitly terminated at the end of a switch case, it continues to execute the statements of the following case. While this is sometimes intentional, it often is a mistake which leads to unexpected behavior.
</h5>

<h2>
Noncompliant Code Example
</h2>

<pre>
switch (myVariable) {
  case 1:                              
    foo();
    break;
  case 2:  // Both 'doSomething()' and 'doSomethingElse()' will be executed. Is it on purpose ?
    doSomething();
  default:                               
    doSomethingElse();
    break;
}
</pre>

<h2>
Compliant Solution
</h2>

<pre>
switch (myVariable) {
  case 1:                              
    foo();
    break;
  case 2: 
    doSomething();
    break;
  default:                               
    doSomethingElse();
    break;
}
</pre>

<h2>
Exceptions
</h2>

<pre>
switch (myVariable) {
  case 0:                                // Empty case used to specify the same behavior for a group of cases.
  case 1:                               
    doSomething();
    break;
  case 2:                                // Use of return statement
    return;
  case 3:                                // Use of throw statement
    throw new IllegalStateException();
  default:                               // For the last case, use of break statement is optional 
    doSomethingElse();
}
</pre>

--------



## 649.


*  "Double.longBitsToDouble" should not be used for "int"

system_tags : bug, priority : 4; plugin_rule_key : S2127

<h5><code>Double.longBitsToDouble</code> expects a 64-bit, <code>long</code> argument. Pass it a smaller value, such as an <code>int</code> and the mathematical conversion into a <code>double</code> simply won't work as anticipated because the layout of the bits will be interpreted incorrectly, as if a child were trying to use an adult's gloves.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
int i = 42;
double d = Double.longBitsToDouble(i);  // Noncompliant
</pre>

--------



## 650.


*  Avoid use of deprecated method

system_tags : null, priority : 1; plugin_rule_key : CallToDeprecatedMethod

<h5>Once deprecated, a method should no longer be used as it means
	that the method might be removed sooner or later.</h5>

--------



## 651.


*  Relational operators should be used in "for" loop termination conditions

system_tags : bug,cert,cwe,misra, priority : 3; plugin_rule_key : S888

Testing <code>for</code> loop termination using an equality operator (<code>==</code> and <code>!=</code>) is dangerous, because it could set up an infinite loop. Using a relational operator instead casts a wider net, and makes it harder (but not impossible) to accidentally write an infinite loop.

<h2>Noncompliant Code Example</h2>
<pre>
for (int i = 1; i != 10; i += 2)  // Noncompliant. Infinite; i goes from 9 straight to 11.
{
  //...
} 
</pre>

<h2>Compliant Solution</h2>
<pre>
for (int i = 1; i &lt;= 10; i += 2)  // Compliant
{
  //...
} 
</pre>

<h2>Exceptions</h2>
An equality operator may be used if the loop counter is not modified within the body of the loop and either:
<ul>
<li>starts below the ending value and is incremented by 1 on each iteration.</li>
<li>starts above the ending value and is decremented by 1 on each iteration.</li>
</ul>

<h2>See</h2>
<ul>
<li><a href="http://cwe.mitre.org/data/definitions/835" target="_blank">MITRE, CWE-835</a> - Loop with Unreachable Exit Condition ('Infinite Loop')</li>
<li><a href="https://www.securecoding.cert.org/confluence/x/EwDJAQ" target="_blank">CERT, MSC21-C</a> - Use robust loop termination conditions</li>
<li><a href="https://www.securecoding.cert.org/confluence/x/GwDJAQ" target="_blank">CERT, MSC21-CPP</a> - Use inequality to terminate a loop whose counter changes by more than one</li>
</ul>

--------



## 652.


*  Public methods should throw at most one checked exception

system_tags : error-handling, priority : 2; plugin_rule_key : S1160

<h5>
Using checked exceptions forces method callers to deal with errors, either by propagating them or by handling them.
This makes those exceptions fully part of the API of the method.
</h5>

<p>
To keep the complexity for callers reasonable, methods should not throw more than one kind of checked exception.
</p>

<p>The following code:</p>

<pre>
public void delete() throws IOException, SQLException {      // Non-Compliant
  /* ... */
}
</pre>

<p>should be refactored into:</p>

<pre>
public void delete() throws SomeApplicationLevelException {  // Compliant
  /* ... */
}
</pre>

Overriding methods are not checked by this rule and are allowed to throw several checked exceptions.

--------



## 653.


*  "@Override" annotation should be used on any method overriding (since Java 5) or implementing (since Java 6) another one

system_tags : null, priority : 2; plugin_rule_key : S1161

<h5>Using the <code>@Override</code> annotation is useful for two reasons :</h5>
<ul>
  <li>It elicits a warning from the compiler if the annotated method doesn't actually override anything, as in the case of a misspelling.</li>
  <li>It improves the readability of the source code by making it obvious that methods are overridden.</li>
</ul>
<h2>Noncompliant Code Example</h2>
<pre>
class ParentClass {
  public boolean doSomething(){...}
}
class FirstChildClass extends ParentClass {
  public boolean doSomething(){...}  //Non-Compliant
}
</pre>

<h2>Compliant Solution</h2>
<pre>
class ParentClass {
  public boolean doSomething(){...}
}
class FirstChildClass extends ParentClass {
  @Override
  public boolean doSomething(){...}  //Compliant
}
</pre>

--------



## 654.


*  An abstract class should have both abstract and concrete methods

system_tags : convention, priority : 2; plugin_rule_key : S1694

<h5>The purpose of an abstract class is to provide some heritable behaviors while also defining methods which must be implemented by sub-classes.</h5>

<p>A class with no abstract methods that was made abstract purely to prevent instantiation should be converted to a concrete class (i.e. remove the <code>abstract</code> keyword) with a private constructor.</p>

<p>A class with only abstract methods and no inheritable behavior should be converted to an interface.</p>

<h2>Noncompliant Code Sample</h2>
<pre>
public abstract class Animal {
  abstract void move();
  abstract void feed();
}

public abstract class Color {
  private int red = 0;
  private int green = 0;
  private int blue = 0;

  public int getRed(){
    return red;
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public interface Animal {
  void move();
  void feed();
}

public class Color {
  private int red = 0;
  private int green = 0;
  private int blue = 0;

  private Color (){
  }

  public int getRed() {
    return red;
  }
}

public abstract class Lamp {

  private boolean switchLamp=false;
  public abstract void glow();

  public void flipSwitch() {
    switchLamp = !switchLamp;
    if (switchLamp) {
       glow();
    }
  }
}
</pre>

--------



## 655.


*  Checked Exception should not be thrown

system_tags : error-handling, priority : 2; plugin_rule_key : S1162

<h5>Even if checked exceptions were thought to be a great feature when they were introduced in Java, their usage progressively became controversial.</h5>

<p>In theory, the purpose of checked exceptions is to ensure that errors will be dealt with, either by propagating them or by handling them.
In practice, checked exceptions negatively impact the readability of source code by spreading this error handling/propagation logic everywhere.</p>

<p>This rule verifies that no method throws a checked exception.</p>

<h2>Noncompliant Code Example</h2>

<pre>
public void myMethod1() throws CheckedException {
  ...
  throw new CheckedException(message);   // Non-Compliant
  ...
  throw new IllegalArgumentException(message); //Compliant as IllegalArgumentException is an unchecked exception
}
</pre>

--------



## 656.


*  Class names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00101

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate. This rule allows to check that all class names match a provided regular expression.
</h5>

<p>
The following code snippet illustrates this rule when the regular expression value is "^[A-Z][a-zA-Z0-9]*$":
</p>
<pre>
public class MyFirstClass { ... } // Compliant

public class mySecondClass { ... }    // Non-Compliant
</pre>

--------



## 657.


*  "NullPointerException" should not be explicitly thrown

system_tags : pitfall, priority : 2; plugin_rule_key : S1695

A <code>NullPointerException</code> should indicate that a <code>null</code> value was unexpectedly encountered. Good programming practice dictates that code is structured to avoid NPE's. 

Explicitly throwing <code>NullPointerException</code> forces a method's callers to explicitly catch it, rather than coding to avoid it. Further, it makes it difficult to distinguish between the unexpectedly-encountered <code>null</code> value and the condition which causes the method to purposely throw an NPE.

If an NPE is being thrown to indicate that a parameter to the method should not have been null, use the <code>@NotNull</code> annotation instead.

<h2>Noncompliant Code Sample</h2>
<pre>
public void doSomething (String aString) throws NullPointerException 
{}
</pre>

<h2>Compliant Solution</h2>
<pre>
public void doSomething (@NotNull String aString)
{}
</pre>

--------



## 658.


*  Method names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00100

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate. This rule allows to check that all function/method names match a provided regular expression.
</h5>

<h2>
Noncompliant Code Example
</h2>
<p>
With default provided regular expression: "^[a-z][a-zA-Z0-9]*$":
</p>
<pre>
public void Do_Something() {...}
</pre>

<h2>
Compliant Solution
</h2>
<pre>
public void doSomething(int value) {…}
}
</pre>

<h2>
Exceptions
</h2>
<p>
Overriding methods are excluded.
</p>
<pre>
@Override
public void Do_Something() {...}
</pre>

--------



## 659.


*  "NullPointerException" should not be caught

system_tags : error-handling, priority : 2; plugin_rule_key : S1696

<h5><code>NullPointerException</code> should be avoided, not caught. Any situation in which <code>NullPointerException</code> is explicitly caught can easily be converted to a <code>null</code> test, and any behavior being carried out in the catch block can easily be moved to the "is null" branch of the conditional.</h5>

<h2>Noncompliant Code Sample</h2>
<pre>
public int lengthPlus(String str) {
  int len = 2;
  try {
    len += str.length();
  }
  catch (NullPointerException e) {
    log.info("argument was null");
  }
  return len;
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public int lengthPlus(String str) {
  int len = 2;

  if (str != null) {
    len += str.length();
  }
  else {
    log.info("argument was null");
  }
  return len;
}
</pre>

--------



## 660.


*  Short-circuit logic should be used to prevent null pointer dereferences in conditionals

system_tags : bug, priority : 4; plugin_rule_key : S1697

<h5>When either the equality operator in a null test or the logical operator that follows it is reversed, the code has the appearance of safely null-testing the object before dereferencing it. Unfortunately the effect is just the opposite - the object is null-tested and then dereferenced _only_ if it is null, leading to a guaranteed null pointer dereference.</h5>

<h2>Noncompliant Code Sample</h2>
<pre>
if (str == null && str.length() == 0) {
  System.out.println("String is empty");
}

if (str != null || str.length() > 0) {
 System.out.println("String is not empty");
}
</pre>

<h2>Compliant Solution</h2>
<pre>
if (str == null || str.length() == 0) {
  System.out.println("String is empty");
}

if (str != null && str.length() > 0) {
  System.out.println("String is not empty");
}
</pre>

--------



## 661.


*  Objects should be compared with "equals()"

system_tags : cwe, priority : 2; plugin_rule_key : S1698

<h5>Using the equality (<code>==</code>) and inequality (<code>!=</code>) operators to compare two objects does not check to see if they have the same values. Rather it checks to see if both object references point to exactly the same object in memory. The vast majority of the time, this is not what you want to do. Use the .equals() method to compare the values of two objects or to compare a string object to a string literal.</h5>

<h2>Noncompliant Code Sample</h2>
<pre>
String str1 = "blue";
String str2 = "blue";
String str3 = str1;

if (str1 == str2)
{
  System.out.println("they're both 'blue'"); // this doesn't print because the objects are different
}

if (str1 == "blue")
{
  System.out.println("they're both 'blue'"); // this doesn't print because the objects are different
}

if (str1 == str3)
{
  System.out.println("they're the same object"); // this prints
}
</pre>

<h2>Compliant Solution</h2>
<pre>
String str1 = "blue";
String str2 = "blue";
String str3 = str1;

if (str1.equals(str2))
{
  System.out.println("they're both 'blue'"); // this prints
}

if (str1.equals("blue"))
{
  System.out.println("they're both 'blue'"); // this prints
}

if (str1 == str3)
{
  System.out.println("they're the same object"); // this still prints, but it's probably not what you meant to do
}
</pre>

<h2>Exception</h2>
Comparing two instances of the <code>Class</code> object will not raise an issue.
<pre>
Class c;
if(c == Integer.class) { //No issue raised
}
</pre>

<h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/595.html">MITRE, CWE-595</a> - Comparison of Object References Instead of Object Contents</li>
    </ul>

--------



## 662.


*  Empty arrays and collections should be returned instead of null

system_tags : null, priority : 2; plugin_rule_key : S1168

<h5>
Returning <code>null</code> instead of an actual array or collection forces callers of the method to explicitly test for nullity, making them more complex and less readable.
Moreover, in many cases, <code>null</code> is used as a synonym for empty.
</h5>

<p>The following code:</p>

<pre>
public static Result[] getResults() {
  return null;                             // Non-Compliant
}

public static void main(String[] args) {
  Result[] results = getResults();

  if (results != null) {                   // Nullity test required to prevent NPE
    for (Result result: results) {
      /* ... */
    }
  }
}
</pre>

<p>should be refactored into:</p>

<pre>
public static Result[] getResults() {
  return new Result[0];                    // Compliant
}

public static void main(String[] args) {
  for (Result result: getResults()) {
    /* ... */
  }
}
</pre>

<p>This rule also applies to collections:</p>

<pre>
public static List&lt;Result&gt; getResults() {
  return null;                             // Non-Compliant
}
</pre>

<p>should be refactored into:</p>

<pre>
public static List&lt;Result&gt; getResults() {
  return Collections.emptyList();           // Compliant
}
</pre>

--------



## 663.


*  Strings should be compared using equals()

system_tags : bug, priority : 3; plugin_rule_key : StringEqualityComparisonCheck

<h5>
String literals, just like any other <code>Object</code>, should be compared using the <code>equals()</code> method.
Using <code>==</code> and <code>!=</code> does not work in general.
</h5>

<p>The following code:</p>

<pre>
if (variable == "foo") { /* ... */ }         // Non-Compliant
if (variable != "foo") { /* ... */ }         // Non-Compliant
</pre>

<p>should be refactored into:</p>

<pre>
if ("foo".equals(variable)) { /* ... */ }    // Compliant
if (!"foo".equals(variable)) { /* ... */ }   // Compliant
</pre>

<p>
  This rule is deprecated, use {rule:squid:S1698} instead.
</p>

--------



## 664.


*  Local variables should not shadow class fields

system_tags : pitfall, priority : 2; plugin_rule_key : HiddenFieldCheck

<h5>
Shadowing fields with a local variable is a bad practice reducing code readability: It makes it confusing to know whether the field or the variable is and should be accessed.
</h5>

<p>
The following code illustrates this rule:
</p>

<pre>
class Foo {
  public int myField;

  public Foo(int myField) {                   // Compliant - method parameters are not checked
    this.myField = myField;
  }

  @Override
  public String toString() {
    int myField = 0;                          // Non-Compliant - should be renamed
    return "Foo{MyField: " + myField + "}";
  }
}
</pre>

--------



## 665.


*  Exceptions should not be thrown in finally blocks

system_tags : null, priority : 2; plugin_rule_key : S1163

<h5>
Throwing an exception from within a finally block will mask any exception which was previously thrown in the <code>try</code> or <code>catch</code> block.
The masked's exception message and stack trace will be lost.
</h5>

<p>The following code:</p>

<pre>
try {
  /* some work which end up throwing an exception */
  throw new IllegalArgumentException();
} finally {
  /* clean up */
  throw new RuntimeException();                          // Non-Compliant - will mask the IllegalArgumentException
}
</pre>

<p>should be refactored into:</p>

<pre>
try {
  /* some work which end up throwing an exception */
  throw new IllegalArgumentException();
} finally {
  /* clean up */                                         // Compliant
}
</pre>

--------



## 666.


*  Exception handlers should preserve the original exception

system_tags : error-handling, priority : 2; plugin_rule_key : S1166

<h5>
When handling a caught exception, two mandatory informations should be logged:
</h5>

<ul>
  <li>Some context to ease the reproduction of the issue.</li>
  <li>The original's exception, for its message and stack trace.</lu>
</ul>

<h2>Noncompliant Code Example</h2>

<pre>
 // Noncompliant - exception is lost
try { /* ... */ } catch (Exception e) { LOGGER.info("context"); }

// Noncompliant - context is required
try { /* ... */ } catch (Exception e) { LOGGER.info(e); }

// Noncompliant - exception is lost (only message is preserved)
try { /* ... */ } catch (Exception e) { LOGGER.info(e.getMessage()); }

// Noncompliant - exception is lost
try { /* ... */ } catch (Exception e) { throw new RuntimeException("context"); }
</pre>

<h2>Compliant Solution</h2>

<pre>
try { /* ... */ } catch (Exception e) { LOGGER.info("context", e); }

try { /* ... */ } catch (Exception e) { throw new RuntimeException("context", e); }
</pre>

<h2>Exceptions</h2>

<p>It is allowed to let the exception propagate.</p>

<pre>
try {
  /* ... */
} catch (RuntimeException e) {
  doSomething();
  throw e;
} catch (Exception e) {
  // Conversion into unchecked exception is also allowed
  throw new RuntimeException(e);
}
</pre>

<p>
<code>InterruptedException</code>, <code>NumberFormatException</code>, <code>ParseException</code> and <code>MalformedURLException</code> exceptions are arguably used to indicate nonexceptional outcomes.
As they are part of Java, developers have no choice but to deal with them. This rule does not verify that those particular exceptions are correctly handled.
</p>

<pre>
int myInteger;
try {
  myInteger = Integer.parseInt(myString);
} catch (NumberFormatException e) {
  // It is perfectly acceptable to not handle "e" here
  myInteger = 0;
}
</pre>

--------



## 667.


*  "toString" should not return null

system_tags : bug, priority : 3; plugin_rule_key : S2225

Calling <code>toString</code> on an object should always return a string. Returning <code>null</code> instead contravenes the method's implicit contract.

<h2>Noncompliant Code Example</h2>
<pre>
public override string ToString () {
  if (this.collection.Count == 0) {
    return null; // Noncompliant
  } else {
    // ...
</pre>

<h2>Compliant Solution</h2>
<pre>
public override string ToString () {
  if (this.collection.Count == 0) {
    return "";
  } else {
    // ...
</pre>

--------



## 668.


*  Servlets should never have mutable instance fields

system_tags : bug,cert,multi-threading,struts, priority : 3; plugin_rule_key : S2226

By contract, a servlet container creates one instance of each servlet and then a dedicated thread is attached to each new incoming HTTP request to process this request. So all threads are sharing the servlet instances and by extension instance fields.  To prevent any misunderstanding and unexpected behavior at runtime, all servlet fields should then be either <code>static</code> and/or <code>final</code>, or simply removed.

With Struts 1.X, the same constraint exists on <code>org.apache.struts.action.Action</code>.

<h2>Noncompliant Code Example</h2>
<pre>
public class MyServlet extends HttpServlet {
  private String userName;  //As this field is shared by all users, it's obvious that this piece of information should be managed differently
  ...
}
</pre>

or 

<pre>
public class MyAction extends Action {
  private String userName;  //Same reason
  ...
}
</pre>

<h2>See</h2>
<ul>
	<li><a href="https://www.securecoding.cert.org/confluence/display/java/VNA06-J.+Do+not+use+non-static+member+fields+in+a+servlet">CERT VNA06-J</a> - Do not use non-static member fields in a servlet</li>
</ul>

--------



## 669.


*  Exception classes should be immutable

system_tags : error-handling, priority : 2; plugin_rule_key : S1165

<h5>
Exceptions are meant to represent the application's state at which an error occurred.
</h5>

<p>Making all fields final ensures that this state:</p>

<ul>
  <li>Will be fully defined at the same time the exception is instantiated.</li>
  <li>Won't be updated or corrupted by some bogus error handler.</li>
</ul>

<p>This will enable developers to quickly understand what went wrong.</p>

<p>The following code:</p>

<pre>
public class MyException extends Exception {

  private int status;                               // Non-Compliant

  public MyException(String message) {
    super(message);
  }

  public int getStatus() {
    return status;
  }

  public void setStatus(int status) {
    this.status = status;
  }

}
</pre>

<p>should be refactored into:</p>

<pre>
public class MyException extends Exception {

  private final int status;                         // Compliant

  public MyException(String message, int status) {
    super(message);
    this.status = status;
  }

  public int getStatus() {
    return status;
  }

}
</pre>

--------



## 670.


*  Architectural constraint

system_tags : null, priority : 2; plugin_rule_key : ArchitecturalConstraint

<h5>A source code comply to an architectural model when it fully
	adheres to a set of architectural constraints. A constraint allows to
	deny references between classes by pattern.</h5>
<p>You can for instance use this rule to :</p>
<ul>
	<li>forbid access to **.web.** from **.dao.** classes</li>
	<li>forbid access to java.util.Vector, java.util.Hashtable and
		java.util.Enumeration from any classes</li>
	<li>forbid access to java.sql.** from **.ui.** and **.web.**
		classes</li>
</ul>

--------



## 671.


*  Control flow statements "if", "for", "while", "switch" and "try" should not be nested too deeply

system_tags : brain-overload, priority : 1; plugin_rule_key : S134

<h5>
Nested <code>if</code>, <code>for</code>, <code>while</code> and <code>try</code> statements is a key ingredient for making what's known as "Spaghetti code".
Such code is hard to read, refactor and therefore maintain.
</h5>

<h2>Noncompliant Code Example</h2>

<p>The following code snippet illustrates this rule with the default threshold of 3.</p>

<pre>
public void process() {
  if (condition1) {                  // Compliant - depth = 1
    /* ... */
    if (condition2) {                // Compliant - depth = 2
      /* ... */
      for(int i = 0; i < 10; i++) {  // Compliant - depth = 3, not exceeding the limit
        /* ... */
        if (condition4) {            // Non-Compliant - depth = 4
          if (condition5) {          // Depth = 5, exceeding the limit, but issues are only reported on depth = 4
            /* ... */
          }
          return;
        }
      }
    }
  }
}
</pre>

--------



## 672.


*  "Cloneables" should implement "clone"

system_tags : bug, priority : 3; plugin_rule_key : S2157

<h5>Simply implementing <code>Cloneable</code>  without also overriding <code>Object.clone()</code> does not necessarily make the class cloneable. While the <code>Cloneable</code> interface does not include a <code>clone</code> method, it is required by convention, and ensures true cloneability. Otherwise the default JVM <code>clone</code> will be used, which copies primitive values and object references from the source to the target. I.e. without overriding <code>clone</code>, any cloned instances will potentially share members with the source instance.</h5>

<p>Removing the <code>Cloneable</code> implementation and providing a good copy constructor is another viable (some say preferable) way of allowing a class to be copied.</p>

<h2>Noncompliant Code Example</h2>
<pre>
class Team implements Cloneable {  // Noncompliant
  private Person coach;
  private List&lt;Person&gt; players;
  public void addPlayer(Person p) {...}
  public Person getCoach() {...}
}
</pre>

<h2>Compliant Solution</h2>
<pre>
class Team implements Cloneable {
  private Person coach;
  private List&lt;Person&gt; players;
  public void addPlayer(Person p) { ... }
  public Person getCoach() { ... }

  @Override
  public Object clone() { 
    Team clone = (Team) super.clone();
    //...
  }
}
</pre>

--------



## 673.


*  Unused method parameters should be removed

system_tags : misra,unused, priority : 2; plugin_rule_key : S1172

<h5>Unused parameters are misleading. Whatever the value passed to such parameters is, the behavior will be the same.</h5>

<h2>Noncompliant Code Example</h2>

<pre>
void doSomething(int a, int b) {     // "b" is unused
  compute(a);
}
</pre>

<h2>Compliant Solution</h2>

<pre>
void doSomething(int a) { 
  compute(a);
}
</pre>

<h2>Exceptions</h2>

<p>Override and implementation methods are excluded, as are methods that are intended to be overridden.</p>

<pre>
@Override
void doSomething(int a, int b) {     // no issue reported on b
  compute(a);
}

public void foo(String s) {
  // designed to be extended but noop in standard case
}

protected void bar(String s) {
  //open-closed principle
}

public void qix(String s) {
  throw new UnsupportedOperationException("This method should be implemented in subclasses");
}
</pre>

--------



## 674.


*  Constants should be declared "final static" rather than merely "final"

system_tags : null, priority : 2; plugin_rule_key : S1170

<h5>
Making a constant just <code>final</code> as opposed to <code>static final</code> leads to duplicating its value for every instance of the class,
uselessly increasing the amount of memory required to execute the application.
</h5>

<h2>Noncompliant Code Example</h2>

<pre>
public class Myclass {
  public final int THRESHOLD = 3;           // Non-Compliant
}
</pre>

<h2>Compliant Solution</h2>

<pre>
public class Myclass {
  public static final int THRESHOLD = 3;    // Compliant
}
</pre>
<h2>Exceptions</h2>
<p>No issues are reported on final fields of inner classes whose type is not a primitive or a String. Indeed according to the Java specification:</p>
<blockquote>An inner class is a nested class that is not explicitly or implicitly declared static. Inner classes may not declare static initializers (&sect; 8.7) or member interfaces. Inner classes may not declare static members, unless they are compile-time constant fields (&sect; 15.28).</blockquote>

--------



## 675.


*  "switch" statements should not have too many "case" clauses

system_tags : brain-overload, priority : 2; plugin_rule_key : S1479

<h5>When <code>switch</code> statements have a large set of <code>case</code> clauses, it is usually an attempt to map two sets of data. A real map structure would be more readable and maintainable, and should be used instead.</h5>

--------



## 676.


*  Non-static class initializers should not be used

system_tags : null, priority : 2; plugin_rule_key : S1171

<h5>
Non-static initializers are rarely used, and can be confusing for most developers.
When possible, they should be refactored into standard constructors or field initializers.
</h5>

<p>The following code:</p>

<pre>
class MyClass {
  private static final Map<String, String> MY_MAP = new HashMap<String, String>() {

    // Non-Compliant - HashMap should be extended only to add behavior, not for initialization
    {
      put("a", "b");
    }

  };
}
</pre>

<p>could be refactored using Guava into:</p>

<pre>
class MyClass {
  // Compliant
  private static final Map<String, String> MY_MAP = ImmutableMap.of("a", "b");
}
</pre>

--------



## 677.


*  Object.finalize() should not be overloaded (by adding method parameters)

system_tags : pitfall, priority : 2; plugin_rule_key : S1175

<h5><code>Object.finalize()</code> is called by the Garbage Collector sometime after the object became unreferenced.</h5>

<p>Overloading this method is misleading:</p>
<ul>
  <li>The overloaded method will not be called by the Garbage Collector.</li>
  <li>Users are not expected to call <code>Object.finalize()</code> and will get confused.</li>
</ul>

<p>Another name should be picked for the method.</p>

<p>The following code:</p>

<pre>
public void finalize(int someParameter) {        // Non-Compliant
  /* ... */
}
</pre>

<p>should be refactored into:</p>

<pre>
public void someBetterName(int someParameter) {  // Compliant
  /* ... */
}
</pre>

--------



## 678.


*  Object.finalize() should remain protected (versus public) when overriding

system_tags : null, priority : 2; plugin_rule_key : S1174

<h5>
The contract of the <code>Object.finalize()</code> method is clear: only the Garbage Collector is supposed to call this method.
Making this method public is misleading, because it implies that any caller can use it.
</h5>

<p>The following code snippet illustrates this rule:</p>

<pre>
public class MyClass {

  @Override
  public void finalize() {    // Non-Compliant
    /* ... */
  }
}
</pre>

--------



## 679.


*  "runFinalizersOnExit" should not be called

system_tags : bug, priority : 4; plugin_rule_key : S2151

<h5>Running finalizers on JVM exit is disabled by default. It can be enabled with <code>System.runFinalizersOnExit</code> and <code>Runtime.runFinalizersOnExit</code>, but both methods are deprecated because they are are inherently unsafe.</h5>

<p>According to the Oracle Javadoc:</p>
<blockquote>
It may result in finalizers being called on live objects while other threads are concurrently manipulating those objects, resulting in erratic behavior or deadlock.
</blockquote>

<p>If you really want to be execute something when the virtual machine begins its shutdown sequence, you should attach a shutdown hook.</p>

<h2>Noncompliant Code Exception</h2>
<pre>
public static void main(String [] args) {
  ...
  System.runFinalizersOnExit(true);  // Noncompliant
  ...
}


protected void finalize(){
  doSomething();
}
</pre>


<h2>Compliant Solution</h2>
<pre>
public static void main(String [] args) {
  Runtime.addShutdownHook(new Runnable() {
    public void run(){
      doSomething();
    }
});
//...
</pre>

--------



## 680.


*  Labels should not be used

system_tags : null, priority : 2; plugin_rule_key : LabelsShouldNotBeUsedCheck

<h5>
Labels are not commonly used in Java, and many developers do not understand how they work.
Moreover, their usage make the control flow harder to follow, which reduces the code's readability.
</h5>

<p>
The following code:
</p>

<pre>
int matrix[][] = {
  {1, 2, 3},
  {4, 5, 6},
  {7, 8, 9}
};

outer: for (int row = 0; row < matrix.length; row++) {   // Non-Compliant
  for (int col = 0; col < matrix[row].length; col++) {
    if (col == row) {
      continue outer;
    }
    System.out.println(matrix[row][col]);                // Prints the elements under the diagonal, i.e. 4, 7 and 8
  }
}
</pre>

<p>
should be refactored into:
</p>

<pre>
for (int row = 1; row < matrix.length; row++) {          // Compliant
  for (int col = 0; col < row; col++) {
    System.out.println(matrix[row][col]);                // Also prints 4, 7 and 8
  }
}
</pre>

--------



## 681.


*  Do not use File#deleteOnExit()

system_tags : null, priority : 2; plugin_rule_key : CallToFileDeleteOnExitMethod

<h5>Usage of method File#deleteOnExit() is not recommended for following reasons:</h5>
<ul>
  <li>The deletion occurs only in case of normal JVM shutdown but not when the JVM is killed or crashes</li>
  <li>For each file handler, the memory associated to this handler is released only at the end of the process</li>
</ul>

--------



## 682.


*  Variables should not be declared and then immediately returned or thrown

system_tags : null, priority : 1; plugin_rule_key : S1488

<h5>Declaring a variable only to immediately return or throw it is a bad practice.
Some developers argue that the practice improves code readability, because it enables them to explicitly name what is being returned. However, this variable is an internal implementation detail that is not exposed to the callers of the method. The method name should be sufficient for callers to know exactly what will be returned.</h5>

<h2>Noncompliant Code Example</h2>

<pre>
public long computeDurationInMilliseconds() {
  long duration = (((hours * 60) + minutes) * 60 + seconds ) * 1000 ;
  return duration;
}

public void doSomething() {
  RuntimeException myException = new RuntimeException();
  throw myException;
}
</pre>
<h2>Compliant Solution</h2>

<pre>
public long computeDurationInMilliseconds() {
  return (((hours * 60) + minutes) * 60 + seconds ) * 1000 ;
}

public void doSomething() {
  throw new RuntimeException();
}
</pre>

--------



## 683.


*  Switch statements should end with a default case

system_tags : cert,cwe,misra, priority : 2; plugin_rule_key : SwitchLastCaseIsDefaultCheck

<h5>
The requirement for a final default clause is defensive programming.
This clause should either take appropriate action or contain a suitable comment as to why no action is taken.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
switch (state) {                       // Non-Compliant - must have a default case
  case 0:
  case 1:
    System.out.println("0 or 1!");
    break;
}

switch (state) {
  default:                             // Non-Compliant - must be last for better readability
    throw new IllegalStateException();
  case 0:
  case 1:
    System.out.println("0 or 1!");
    break;
}

switch (state) {
  case 0:
  case 1:
    System.out.println("0 or 1!");
    break;
  default:                             // Compliant
    throw new IllegalStateException();
</pre>

--------



## 684.


*  Right curly brace and next "else", "catch" and "finally" keywords should be located on two different lines

system_tags : convention, priority : 2; plugin_rule_key : RightCurlyBraceDifferentLineAsNextBlockCheck

<h5>
Sharing some coding conventions is a key point to make it possible for a team to efficiently collaborate.
This rule make it mandatory to place closing curly braces and next <code>else</code>, <code>catch</code> or <code>finally</code> keywords on two different lines.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
public void myMethod() {
  if(something) {
    executeTask();
  } else if (somethingElse) {          // Non-Compliant
    doSomethingElse();
  }
  else {                               // Compliant
     generateError();
  }

  try {
    generateOrder();
  } catch (Exception e) {              // Non-Compliant
    log(e);
  }
  finally {                            // Compliant
    closeConnection();
  }
}
</pre>

--------



## 685.


*  Throwable and Error classes should not be caught

system_tags : error-handling, priority : 4; plugin_rule_key : S1181

<h5>
<code>Throwable</code> is the superclass of all errors and exceptions in Java.
<code>Error</code> is the superclass of all errors which are not meant to be caught by applications.
</h5>

<p>
Catching either <code>Throwable</code> or <code>Error</code> will also catch <code>OutOfMemoryError</code> or <code>InternalError</code> from which an application should not attempt to recover.
</p>

<p>Only <code>Exception</code> and its subclasses should be caught.</p>

<h2>Noncompliant Code Example</h2>

<pre>
try { /* ... */ } catch (Throwable t) { /* ... */ }
try { /* ... */ } catch (Error e) { /* ... */ } 
</pre>

<h2>Compliant Solution</h2>

<pre>
try { /* ... */ } catch (Exception e) { /* ... */ }  
try { /* ... */ } catch (RuntimeException e) { /* ... */ }  
try { /* ... */ } catch (MyException e) { /* ... */ }  
</pre>

--------



## 686.


*  Modifiers should be declared in the correct order

system_tags : convention, priority : 1; plugin_rule_key : ModifiersOrderCheck

<h5>
The Java Language Specification recommends listing modifiers in the following order:
</h5>

<ul>
  <li>Annotations</li>
  <li><code>public</code></li>
  <li><code>protected</code></li>
  <li><code>private</code></li>
  <li><code>abstract</code></li>
  <li><code>static</code></li>
  <li><code>final</code></li>
  <li><code>transient</code></li>
  <li><code>volatile</code></li>
  <li><code>synchronized</code></li>
  <li><code>native</code></li>
  <li><code>strictfp</code></li>
</ul>

<p>
Not following this convention has no technical impact, but will reduce the code's readability because most developers are used to the standard order.
</p>

<p>
The following code:
</p>

<pre>
static public void main(String[] args) {   // Non-Compliant
}
</pre>

<p>
should be refactored into:
</p>

<pre>
public static void main(String[] args) {   // Compliant
}
</pre>

--------



## 687.


*  super.clone() should be called when overriding Object.clone()

system_tags : null, priority : 2; plugin_rule_key : S1182

<h5>The usual convention for <code>Object.clone()</code> according to Oracle's Javadoc is that:</h5>
<ul>
  <li><code>x.clone() != x</code></li>
  <li><code>x.clone().getClass() == x.getClass()</code></li>
  <li><code>x.clone().equals(x)</code></li>
</ul>

<p>Obtaining the object that will be returned by calling <code>super.clone()</code> helps to satisfy those invariants:</p>
<ul>
  <li><code>super.clone()</code> returns a new object instance</li>
  <li><code>super.clone()</code> returns an object of the same type as the one <code>clone()</code> was called on</li>
  <li><code>Object.clone()</code> performs a shallow copy of the object's state</li>
</ul>

<p>For example, the following code:</p>

<pre>
class BaseClass implements Cloneable {
  @Override
  public Object clone() throws CloneNotSupportedException {    // Non-Compliant - should return the super.clone() instance
    return new BaseClass();
  }
}

class DerivedClass extends BaseClass implements Cloneable {
  /* Does not override clone() */

  public void sayHello() {
    System.out.println("Hello, world!");
  }
}

class Application {
  public static void main(String[] args) throws Exception {
    DerivedClass instance = new DerivedClass();
    ((DerivedClass) instance.clone()).sayHello();              // Throws a ClassCastException because invariant #2 is violated
  }
}
</pre>

<p>should be refactored into:</p>

<pre>
class BaseClass implements Cloneable {
  @Override
  public Object clone() throws CloneNotSupportedException {    // Compliant
    return super.clone();
  }
}

class DerivedClass extends BaseClass implements Cloneable {
  /* Does not override clone() */

  public void sayHello() {
    System.out.println("Hello, world!");
  }
}

class Application {
  public static void main(String[] args) throws Exception {
    DerivedClass instance = new DerivedClass();
    ((DerivedClass) instance.clone()).sayHello();              // Displays "Hello, world!" as expected. Invariant #2 is satisfied
  }
}
</pre>

--------



## 688.


*  Redundant casts should not be used

system_tags : null, priority : 1; plugin_rule_key : S1905

<h5>Unnecessary casting expressions make the code harder to read and understand.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public void example() {
  for (Foo obj : (List&lt;Foo&gt;) getFoos()) {  // Noncompliant; cast unnecessary because List&lt;Foo&gt; is what's returned
  //...
  }
}

public List&lt;Foo&gt; getFoos() {
  return this.foos;
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public void example() {
  for (Foo obj : getFoos()) {
    //...
  }
}

public List&lt;Foo&gt; getFoos() {
  return this.foos;
}
</pre>

<h2>Exceptions</h2>
<p>Casting may be required to distinguish the method to call in the case of overloading:</p>
<pre>
class A {}
class B extends A{}
class C {
  void fun(A a){}
  void fun(B b){}

  void foo() {
    B b = new B();
    fun(b);
    fun((A) b); //call the first method so cast is not redundant.
  }
}
</pre>

--------



## 689.


*  Methods should not be empty

system_tags : null, priority : 2; plugin_rule_key : S1186

<h5>There are three reasons for a method not to have a method body:</h5>

<ul>
  <li>It is an unintentional omission, and should be fixed.</li>
  <li>It is not yet, or never will be, supported. In this case an <code>UnsupportedOperationException</code> should be thrown.</li>
  <li>The method is an intentionally-blank override. In this case a nested comment should explain the reason for the blank override.</li>
</ul>

<p>The following code snippet:</p>

<pre>
// Non-Compliant
public void doSomething() {
}
</pre>

should be refactored into:

<pre>
// Compliant
@Override
public void doSomethingElse() {
  // Do nothing because of X and Y.
}
</pre>

or:

<pre>
// Compliant
@Override
public void doSomethingElse() {
  throw new UnsupportedOperationException();
}
</pre>

<p>Empty methods not having any nested comments are tolerated in Abstract classes as those empty methods are usual when implementing the visitor pattern.</p>

--------



## 690.


*  Return values should not be ignored when function calls don't have any side effects

system_tags : bug, priority : 3; plugin_rule_key : S2201

<h5>When the call to a function doesn't have any side effect, what is the point of ignoring the result of the function call ? In such case, either the function call is useless and should be dropped or the source code doesn't behave as expected.</h5>

<p>To prevent generating any false-positives, this rule triggers an issues only on the following predefined list of immutable classes in the Java API : String, Boolean, Integer, Double, Float, Byte, Character, Short, StackTraceElement.</p>

<h2>Noncompliant Code Example</h2>
<pre>
public void handle(String command){
  command.toLowerCase(); // Noncompliant; result of method thrown away
  ...
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public void handle(String command){
  String formattedCommand = command.toLowerCase();
  ...
}
</pre>

--------



## 691.


*  Overriding methods should do more than simply call the same method in the super class

system_tags : brain-overload, priority : 1; plugin_rule_key : S1185

<h5>Overriding a method just to call the same method from the super class without performing any other actions is useless and misleading.</h5>

<p>The following code snippet illustrates this rule:</p>

<pre>
public void doSomething() {                     // Non-Compliant
  super.doSomething();
}

@Override
public boolean isLegal(Action action) {         // Non-Compliant
  return super.isLegal(action);
}

@Override
public boolean isLegal(Action action) {         // Compliant - not simply forwarding the call
  return super.isLegal(new Action(/* ... */));
}

@Id
@Override
public int getId() {                            // Compliant - there is annotation different from @Override
  return super.getId();
}
</pre>

--------



## 692.


*  Two cases in the same "switch" should not have exactly the same implementation

system_tags : bug, priority : 2; plugin_rule_key : S1871

<h5>Having two cases in the same switch statement with the same implementation is at best duplicate code, and at worst a coding error. If the same logic is truly needed for both cases, then one should fall through to the other.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
switch (i) {
  case 1:
    doSomething();
    break;
  case 2:
    doSomethingDifferent();
    break;
  case 3:  // Noncompliant; duplicates case 1's implementation
    doSomething();
    break;
}
</pre>

<h2>Compliant Solution</h2>
<pre>
switch (i) {
  case 1:
  case 3:
    doSomething();
    break;
  case 2:
    doSomethingDifferent();
    break;
}
</pre>
or
<pre>
switch (i) {
  case 1:
    doSomething();
    break;
  case 2:Check
    doSomethingDifferent();
    break;
  case 3:
    doThirdThing();
    break;
}
</pre>

--------



## 693.


*  Lambdas and anonymous classes should not have too many lines

system_tags : brain-overload, priority : 2; plugin_rule_key : S1188

<h5>
Anonymous classes and lambdas (with Java 8) are a very convenient and compact way to inject a behavior without having to create a dedicated class. But those anonymous inner classes and lambdas should be used only if the behavior to be injected can be defined in a few lines of code, otherwise the source code can quickly become unreadable.
</h5>

--------



## 694.


*  ".equals()" should not be used to test the values of "Atomic" classes

system_tags : bug, priority : 4; plugin_rule_key : S2204

<h5><code>AtomicInteger</code>, and <code>AtomicLong</code> extend <code>Number</code>, but they're distinct from <code>Integer</code> and <code>Long</code> and should be handled differently. <code>AtomicInteger</code> and <code>AtomicLong</code> are designed to support lock-free, thread-safe programming on single variables. As such, an <code>AtomicInteger</code> will only ever be "equal" to itself. Instead, you should <code>.get()</code> the value and make comparisons on it.</h5>

<p>This applies to all the atomic, seeming-primitive wrapper classes: <code>AtomicInteger</code>, <code>AtomicLong</code>, and <code>AtomicBoolean</code>.</p>

<h2>Noncompliant Code Example</h2>
<pre>
AtomicInteger aInt1 = new AtomicInteger(0);
AtomicInteger aInt2 = new AtomicInteger(0);

if (aInt1.equals(aInt2)) { ... }  // Noncompliant
</pre>

<h2>Compliant Solution</h2>
<pre>
AtomicInteger aInt1 = new AtomicInteger(0);
AtomicInteger aInt2 = new AtomicInteger(0);

if (aInt1.get() == aInt2.get()) { ... }
</pre>

--------



## 695.


*  "static final" arrays should be "private"

system_tags : cwe,security, priority : 3; plugin_rule_key : S1873

<h5>Public arrays, even ones declared <code>static final</code> can have their contents edited by malicious programs. The <code>final</code> keyword on an array declaration means that the array object itself may only be assigned once, but its contents are still mutable. Therefore making arrays <code>public</code> is a security risk.</h5>

<p>Instead, arrays should be private and accessed through methods.</p>

<h2>Noncompliant Code Example</h2>
<pre>
public class Estate {
  // Noncompliant; array contents can be modified
  public static final String [] HEIRS = new String [] {
    "Betty", "Suzy" };
  }
}

public class Malicious {
  public void changeWill() {
    Estate.HEIRS[0] = "Biff";
    if (Estate.HEIRS.length > 1) {
      for (int i = 1; i < Estate.HEIRS.length; i++) {
        Estate.HEIRS[i] = "";
      }
    }
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class Estate {
  private static final String [] HEIRS = new String [] {
    "Betty", "Suzy" };

  public String [] getHeirs() {
    // return copy of HEIRS
  }
}
</pre>

<h2>See</h2>
<ul>
  <li><a href="http://cwe.mitre.org/data/definitions/582.html">MITRE, CWE-582</a></li>
</ul>

--------



## 696.


*  Useless imports should be removed

system_tags : unused, priority : 1; plugin_rule_key : UselessImportCheck

<h5>
The imports part of a file should be handled by the Integrated Development Environment (IDE), not manually by the developer.
Unused and useless imports should not occur if that is the case.
Leaving them in reduces the code's readability, since their presence can be confusing.
</h5>

<p>The following code snippet illustrates this rule:</p>

<pre>
package my.company;

import java.lang.String;        // Non-Compliant - java.lang classes are always implicitly imported
import my.company.SomeClass;    // Non-Compliant - same package files are always implicitly imported
import java.io.File;            // Non-Compliant - File is not used

import my.company2.SomeType;
import my.company2.SomeType;    // Non-Compliant - 'SomeType' is already imported

class ExampleClass {

  public String someString;
  public SomeType something;

}
</pre>

--------



## 697.


*  "compareTo" results should not be checked for specific values

system_tags : bug, priority : 2; plugin_rule_key : S2200

While most <code>compareTo</code> methods return -1, 0, or 1, some do not, and testing the result of a <code>compareTo</code> against a specific value other than 0 could result in false negatives.

<h2>Noncompliant Code Example</h2>
<pre>
if (myClass.compareTo(arg) == -1) {  // Noncompliant
  // ...
}
</pre>

<h2>Compliant Solution</h2>
<pre>
if (myClass.compareTo(arg) &lt; 0) {
  // ...
}
</pre>

--------



## 698.


*  Deprecated elements should have both the annotation and the Javadoc tag

system_tags : null, priority : 2; plugin_rule_key : MissingDeprecatedCheck

<h5>Deprecation should be marked with both the <code>@Deprecated</code> annotation and @deprecated Javadoc tag. The annotation enables tools such as IDEs to warn about referencing deprecated elements, and the tag can be used to explain when it was deprecated, why, and how references should be refactored.</h5>

<p>The following code illustrates this rule:</p>

<h2>Noncompliant Code Sample</h2>
<pre>
class MyClass {

@Deprecated
public void foo1() {
}

/**
* @deprecated
*/
public void foo2() {    // Non-Compliant
}

}
</pre>

<h2>Compliant Solution</h2>
<pre>
class MyClass {

/**
* @deprecated (when, why, refactoring advice...)
*/
@Deprecated
public void foo1() {
}

/**
* @deprecated (when, why, refactoring advice...)
*/
@Deprecated
public void foo2() {    // Non-Compliant
}

}
</pre>

<h2>Exceptions</h2>
<p>The members and methods of a deprecated class or interface are ignored by this rule. The classes and interfaces themselves are still subject to it.</p>

<pre>
/**
* @deprecated (when, why, &etc...)
*/
@Deprecated
class Qix  {

public void foo() {} // Compliant; class is deprecated

}

/**
* @deprecated (when, why, &etc...)
*/
@Deprecated
interface Plop {

void bar();

}
</pre>

--------



## 699.


*  Unused local variables should be removed

system_tags : unused, priority : 2; plugin_rule_key : S1481

<h5>
If a local variable is declared but not used in the program, it can be considered dead code and should therefore be removed.
This will improve maintainability because developers will not wonder what the variable is used for.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public int compute(int a){
  int foo = 6;
  return a * 4;
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public int compute(int a){
  return a * 4;
}
</pre>

--------



## 700.


*  The ternary operator should not be used

system_tags : brain-overload, priority : 2; plugin_rule_key : S1774

<h5>While the ternary operator is pleasingly compact, it's use can make code more difficult to read. It should therefore be avoided in favor of the more verbose <code>if</code>/<code>else</code> structure.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
System.out.println(i>10?"yes":"no");
</pre>

<h2>Compliant Solution</h2>
<pre>
if (i > 10) {
  System.out.println(("yes");
} else {
  System.out.println("no");
}
</pre>

--------



## 701.


*  "Iterator.next()" methods should throw "NoSuchElementException"

system_tags : bug, priority : 2; plugin_rule_key : S2272

By contract, any implementation of the <code>java.util.Iterator.next()</code> method should throw a <code>NoSuchElementException</code> exception when the iteration has no more elements. Any other behavior when the iteration is done could lead to unexpected behavior for users of this <code>Iterator</code>. 

<h2>Noncompliant Code Example</h2>
<pre>
public class MyIterator implements Iterator&lt;String&gt;{
  ...
  public String next(){
    if(!hasNext()){
      return null;
    }
    ...
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class MyIterator implements Iterator&lt;String&gt;{
  ...
  public String next(){
    if(!hasNext()){
      throw new NoSuchElementException();
    }
    ...
  }
}
</pre>

--------



## 702.


*  "wait(...)", "notify()" and "notifyAll()" methods should only be called when a lock is obviously held on an object

system_tags : bug,multi-threading, priority : 3; plugin_rule_key : S2273

<h5>By contract, the method <code>Object.wait(...)</code>, <code>Object.notify()</code> and <code>Object.notifyAll()</code> should be called by a thread that is the owner of the object's monitor. If this is not the case an <code>IllegalMonitorStateException</code> exception is thrown. This rule reinforces this constraint by making it mandatory to call one of these methods only inside a <code>synchronized</code> method or statement.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
private void removeElement() {
  while (!suitableCondition()){
    obj.wait();
  }
  ... // Perform removal
}
</pre>

or

<pre>
private void removeElement() {
  while (!suitableCondition()){
    wait();
  }
  ... // Perform removal
}
</pre>

<h2>Compliant Solution</h2>
<pre>
private void removeElement() {
  synchronized(obj) {
    while (!suitableCondition()){
      obj.wait();
    }
    ... // Perform removal
  }
}
</pre>

or

<pre>
private synchronized void removeElement() {
  while (!suitableCondition()){
    wait();
  }
  ... // Perform removal
}
</pre>

--------



## 703.


*  Long suffix "L" should be upper case

system_tags : convention, priority : 2; plugin_rule_key : LowerCaseLongSuffixCheck

<h5>
The long suffix should always be written in upper case, i.e. 'L', as the lower case 'l' can easily be confused with the digit one '1'.
</h5>

<p>
The following code:
</p>

<pre>
long n = 10l;  // Non-Compliant - easily confused with one zero one
</pre>

<p>
should be refactored into:
</p>

<pre>
long n = 10L;  // Compliant
</pre>

--------



## 704.


*  Utility classes should not have a public constructor

system_tags : null, priority : 2; plugin_rule_key : S1118

<h5>
Utility classes, which are a collection of static members, are not meant to be instantiated.
Even abstract utility classes, which can be extended, should not have public constructors.
</h5>

<p>
Java adds an implicit public constructor to every class which does not define at least one explicitly.
Hence, at least one non-public constructor should be defined.
</p>
</p>

<p>The following code:</p>

<pre>
class StringUtils { // Non-Compliant

  public static String concatenate(String s1, String s2) {
    return s1 + s2;
  }

}
</pre>

<p>should be refactored into:</p>

<pre>
class StringUtils { // Compliant

  private StringUtils() {
  }

  public static String concatenate(String s1, String s2) {
    return s1 + s2;
  }

}
</pre>

--------



## 705.


*  Cryptographic RSA algorithms should always incorporate OAEP (Optimal Asymmetric Encryption Padding)

system_tags : cwe,owasp-top10,security, priority : 3; plugin_rule_key : S2277

<h5>Without OAEP in RSA encryption, it takes less work for an attacker to decrypt the data or infer patterns from the ciphertext.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
Cipher rsa = javax.crypto.Cipher.getInstance("RSA/NONE/NoPadding");
</pre>

<h2>Compliant Solution</h2>
<pre>
Cipher rsa = javax.crypto.Cipher.getInstance("RSA/ECB/OAEPWithSHA-1AndMGF1Padding");
</pre>
<h2>See</h2>
<ul>
  <li><a href="http://cwe.mitre.org/data/definitions/780.html">MITRE CWE-780</a> - Use of RSA Algorithm without OAEP</li>
  <li><a href="http://cwe.mitre.org/data/definitions/327.html">MITRE CWE-327</a> - Use of a Broken or Risky Cryptographic Algorithm</li>
  <li><a href="https://www.owasp.org/index.php/Top_10_2013-A6-Sensitive_Data_Exposure">OWASP Top Ten 2013 Category A6</a> - Sensitive Data Exposure</li>
</ul>

--------



## 706.


*  Unused protected method

system_tags : unused, priority : 2; plugin_rule_key : UnusedProtectedMethod

<h5>Protected methods that are never used by any classes in the same
  project are strongly suspected to be dead code. Dead code means
  unnecessary, inoperative code that should be removed. This helps in
  maintenance by decreasing the maintained code size, making it easier to
  understand the program and preventing bugs from being introduced.</h5>
<p>In the following case, unused protected methods are not
  considered as dead code by SonarQube :</p>
<ul>
  <li>Protected methods which override a method from a parent class.</li>
  <li>Protected methods of an abstract class.</li>
</ul>

--------



## 707.


*  "wait(...)" should be used instead of "Thread.sleep(...)" when a lock is held

system_tags : bug,multi-threading, priority : 3; plugin_rule_key : S2276

<h5>If <code>Thread.sleep(...)</code> is called when the current thread holds a lock, it could lead to performance, and scalability issues, or even worse to deadlocks because the execution of the thread holding the lock is frozen. It's better to call {{wait(...)}} on the monitor object to temporarily release the lock and allow other threads to run.</h5>

<h2>Noncompliant Code Sample</h2>
<pre>
public void doSomething(){
  synchronized(monitor) {
    while(notReady()){
    Thread.sleep(200);
  }
  process();
}
...
}
</pre>


<h2>Compliant Solution</h2>
<pre>
public void doSomething(){
  synchronized(monitor) {
    while(notReady()){
    monitor.wait(200);
  }
  process();
}
...
}
</pre>

--------



## 708.


*  Printf-style format strings should not lead to any runtime unexpected behavior

system_tags : bug,pitfall, priority : 3; plugin_rule_key : S2275

<h5>Because <code>printf</code>-style format strings are interpreted at runtime, rather than validated by the Java compiler, they can contain errors that lead to unexpected behavior or runtime errors. This rule statically validates the good behavior of <code>printf</code>-style formats when calling the <code>format(...)</code> methods of <code>java.util.Formatter</code>, <code>java.lang.String</code>, <code>java.io.PrintStream</code> and <code>java.io.PrintWriter</code> classes and the <code>printf(...)</code> methods of <code>java.io.PrintStream</code> or <code>java.io.PrintWriter</code> classes.</h5>

<h2>Noncompliant Code Exemple</h2>
<pre>
String.format("The value of my integer is %d", "Hello World");  // Noncompliant; an 'int' is expected rather than a String
String.format("First {0} and then {1}", "foo", "bar");  //Noncompliant. Looks like there is a confusion with the use of <code>java.text.MessageFormat</code>, parameters "foo" and "bar" will be simply ignored here
String.format("Duke's Birthday year is %tX", c);  //Noncompliant; X is not a supported time conversion character
String.format("Display %3$d and then %d", 1, 2, 3);   //Noncompliant; the second argument '2' is unused
String.format("Too many arguments %d and %d", 1, 2, 3);  //Noncompliant; the third argument '3' is unused
String.format("Not enough arguments %d and %d", 1);  //Noncompliant; the second argument is missing
String.format("First Line\n");   //Noncompliant; %n should be used in place of \n to produce the platform-specific line separator
String.format("%< is equals to %d", 2);   //Noncompliant; the argument index '<' refers to the previous format specifier but there isn't one
String.format("Is myObject null ? %b", myObject);   //Noncompliant; when a non-boolean argument is formatted with %b, it prints true for any nonnull value, and false for null. Even if intended, this is misleading. It's better to directly inject the boolean value (myObject == null in this case)
</pre>

<h2>Compliant Solution</h2>
<pre>
String.format("The value of my integer is %d", 3);
String.format("First %s and then %s", "foo", "bar");
String.format("Duke's Birthday year is %tY", c);
String.format("Display %2$d and then %d", 1, 3);
String.format("Too many arguments %d %d", 1, 2);
String.format("Not enough arguments %d and %d", 1, 2);
String.format("First Line%n");
String.format("%d is equals to %<", 2);
String.format("Is myObject null ? %b", myObject == null);
</pre>

--------



## 709.


*  "Object.wait(...)" and "Condition.await(...)" should always be called inside a "while" loop

system_tags : bug,cert,multi-threading, priority : 3; plugin_rule_key : S2274

<h5>According to the Java <code>Condition</code> interface documentation:</h5>
<blockquote>
When waiting upon a <code>Condition</code>, a "spurious wakeup" is permitted to occur, in general, as a concession to the underlying platform semantics. This has little practical impact on most application programs as a Condition should always be waited upon in a loop, testing the state predicate that is being waited for. An implementation is free to remove the possibility of spurious wakeups but it is recommended that applications programmers always assume that they can occur and so always wait in a loop.
</blockquote>

The same advice is also found for the <code>Object.wait(...)</code> method:
<blockquote>
waits should always occur in loops, like this one:
<pre>
synchronized (obj) {
  while (&lt;condition does not hold&gt;){
    obj.wait(timeout);
  }
  ... // Perform action appropriate to condition
}
  </pre>
</blockquote>

<h2>Noncompliant Code Example</h2>
<pre>
  synchronized (obj) {
    if (!suitableCondition()){
      obj.wait(timeout);   //the thread can wakeup whereas the condition is still false
    }
    ... // Perform action appropriate to condition
  }
</pre>

<h2>Compliant Solution</h2>
<pre>
synchronized (obj) {
  while (!suitableCondition()){
   obj.wait(timeout);
  }
  ... // Perform action appropriate to condition
}
</pre>

<h2>See</h2>
    <ul>
      <li><a href="https://www.securecoding.cert.org/confluence/display/java/THI03-J.+Always+invoke+wait%28%29+and+await%28%29+methods+inside+a+loop">CERT THI03-J</a> - Always invoke wait() and await() methods inside a loop</li>
    </ul>

--------



## 710.


*  Avoid commented-out lines of code

system_tags : unused, priority : 2; plugin_rule_key : CommentedOutCodeLine

<h5>Here are the main reasons why commented code is a code smell :</h5>
<ul>
    <li>It always raises more questions than it gives answers</li>
    <li>Everybody will forget very quickly how relevant the commented code is</li>
    <li>This is distraction when going down the code as it stops the flow of eyes</li>
    <li>It is a bad SCM engine : Subversion, CVS and Git are really more trustworthy !</li>
    <li>The simple fact of understanding why code was commented out in the first place can take a lot of time</li>
</ul>

--------



## 711.


*  DES (Data Encryption Standard) and DESede (3DES) should not be used

system_tags : cwe,owasp-top10,security, priority : 3; plugin_rule_key : S2278

<h5>According to the US National Institute of Standards and Technology (NIST), the Data Encryption Standard (DES) is no longer considered secure:</h5>
<blockquote>
Adopted in 1977 for federal agencies to use in protecting sensitive, unclassified information, the DES is being withdrawn because it no longer provides the security that is needed to protect federal government information.
Federal agencies are encouraged to use the Advanced Encryption Standard, a faster and stronger algorithm approved as FIPS 197 in 2001.
</blockquote>

<h2>Noncompliant Code Example</h2>
<pre>
Cipher c = Cipher.getInstance("DESede/ECB/PKCS5Padding");
</pre>

<h2>Compliant Solution</h2>
<pre>
Cipher c = Cipher.getInstance("AES/GCM/NoPadding");
</pre>

<h2>See</h2>
<ul>
  <li><a href="http://cwe.mitre.org/data/definitions/326.html">MITRE CWE-326</a> - Inadequate Encryption Strength</li>
  <li><a href="https://www.owasp.org/index.php/Top_10_2013-A6-Sensitive_Data_Exposure">OWASP Top Ten 2013 Category A6</a> - Sensitive Data Exposure</li>
</ul>

--------



## 712.


*  Variables should not be self-assigned

system_tags : bug, priority : 2; plugin_rule_key : S1656

<h5>There is no reason to re-assign a variable to itself. Either this statement is redundant and should be removed, or the re-assignment is a mistake and some other value was intended for the assignment instead.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public void setName(String name) {
  name = name;
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public void setName(String name) {
  this.name = name;
}
</pre>

--------



## 713.


*  Literal boolean values should not be used in condition expressions

system_tags : null, priority : 1; plugin_rule_key : S1125

<h5>
Remove literal boolean values from conditional expressions to improve readability. Anything that can be tested for equality with a boolean value must itself be a boolean value, and boolean values can be tested atomicly.
</h5>

<h2>Noncompliant Code Example</h2>

<pre>
if (booleanVariable == true) { /* ... */ }
if (booleanVariable != true) { /* ... */ }
if (booleanVariable || false) { /* ... */ }
doSomething(!false);
</pre>

<h2>Compliant Solution</h2>

<pre>
if (booleanVariable) { /* ... */ }
if (!booleanVariable) { /* ... */ }
if (booleanVariable) { /* ... */ }
doSomething(true);
</pre>

--------



## 714.


*  Return of boolean expressions should not be wrapped into an if-then-else statement

system_tags : null, priority : 2; plugin_rule_key : S1126

<h5>
Return of boolean literal statements wrapped into <code>if-then-else</code> ones should be simplified.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
if (expression) {
  return true;
} else {
  return false;
}
</pre>

<h2>Compliant Solution</h2>

<pre>
return expression;   
</pre>

--------



## 715.


*  Class variable fields should not have public accessibility

system_tags : null, priority : 2; plugin_rule_key : ClassVariableVisibilityCheck

<h5>
Public class variable fields do not respect the encapsulation principle and has two main disadvantages:
</h5>

<ul>
  <li>Additional behavior such as validation cannot be added.</li>
  <li>The internal representation is exposed, and cannot be changed afterwards.</li>
</ul>

<p>The following code:</p>

<pre>
public class MyClass {

  public static final int SOME_CONSTANT = 0;     // Compliant - constants are not checked

  public String firstName;                       // Non-Compliant

}
</pre>

<p>should be refactored into:</p>

<pre>
public class MyClass {

  public static final int SOME_CONSTANT = 0;     // Compliant - constants are not checked

  private String firstName;                      // Compliant

  public String getFirstName() {
    return firstName;
  }

  public void setFirstName(String firstName) {
    this.firstName = firstName;
  }

}
</pre>

--------



## 716.


*  "ConcurrentLinkedQueue.size()" should not be used

system_tags : performance, priority : 3; plugin_rule_key : S2250

<h5>For most collections the <code>size()</code> method requires constant time, but the time required to execute <code>ConcurrentLinkedQueue.size()</code> is directly proportional to the number of elements in the queue. When the queue is large, this could therefore be an expensive operation. Further, the results may be inaccurate if the queue is modified during execution.</h5>

<p>By the way, if the <code>size()</code> is used only to check that the collection is empty, then the <code>isEmpty()</code> method should be used.</p>

<h2>Noncompliant Code Example</h2>
<pre>
ConcurrentLinkedQueue queue = new ConcurrentLinkedQueue();
//...
log.info("Queue contains " + queue.size() + " elements");
</pre>

--------



## 717.


*  Strings should not be concatenated using '+' in a loop

system_tags : performance, priority : 2; plugin_rule_key : S1643

<h5>Strings are immutable objects in Java, so concatenation doesn't simply add the new String to the end of the existing string. Instead, in each loop iteration, the first String is converted to an intermediate object type, the second string is appended, and then the intermediate object is converted back to a String. Further, performance of these intermediate operations degrades as the String gets longer. Therefore, the use of StringBuilder is preferred.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
String str = "";
for (int i = 0; i < arrayOfStrings.length ; ++i) {
  str = str + arrayOfStrings[i];
}
</pre>

<h2>Compliant Solution</h2>
<pre>
StringBuilder bld = new StringBuilder();
for (int i = 0; i < arrayOfStrings.length; ++i) {
  bld.append(arrayOfStrings[i]);
}
String str = bld.toString();
</pre>

--------



## 718.


*  A "for" loop update clause should move the counter in the right direction

system_tags : bug, priority : 4; plugin_rule_key : S2251

A <code>for</code> loop with a counter that moves in the wrong direction is not an infinite loop. Because of wraparound, the loop will eventually reach its stop condition, but in doing so, it will run many, many more times than anticipated, potentially causing unexpected behavior. 

<h2>Noncompliant Code Example</h2>
<pre>
public void doSomething(String [] strings) {
  for (int i = 0; i &lt; strings.length; i--) { // Noncompliant;
    String string = strings[i];  // ArrayIndexOutOfBoundsException when i reaches -1
    //...
  }
</pre>

<h2>Compliant Solution</h2>
<pre>
public void doSomething(String [] strings) {
  for (int i = 0; i &lt; strings.length; i++) {
    String string = strings[i];
    //...
  }
</pre>

--------



## 719.


*  Generic exceptions Error, RuntimeException, Throwable and Exception should never be thrown

system_tags : error-handling, priority : 2; plugin_rule_key : S00112

<h5>
Using such generic exception prevents calling methods from handling differently each kind of error.
</h5>

<h2>
Noncompliant Code Example
</h2>

<pre>
public void foo(String bar) throws Throwable { // Noncompliant
  throw new RuntimeException("My Message");    // Noncompliant
}
</pre>

<h2>
Compliant Solution
</h2>

<pre>
public void foo(String bar) {
  throw new MyOwnRuntimeException("My Message");
}
</pre>

<h2>
Exceptions
</h2>

<p>
Generic exceptions in signature of overriding methods are excluded
</p>

<pre>
@Override
public void myMethod() throws Exception {...}
</pre>

--------



## 720.


*  "BigDecimal(double)" should not be used

system_tags : bug, priority : 3; plugin_rule_key : S2111

<h5>Because of floating point imprecision, you're unlikely to get the value you expect from the <code>BigDecimal(double)</code> constructor.</h5>

<p>From <a href="http://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#BigDecimal(double)">the JavaDocs</a>:</p>

<blockquote>The results of this constructor can be somewhat unpredictable. One might assume that writing new BigDecimal(0.1) in Java creates a BigDecimal which is exactly equal to 0.1 (an unscaled value of 1, with a scale of 1), but it is actually equal to 0.1000000000000000055511151231257827021181583404541015625. This is because 0.1 cannot be represented exactly as a double (or, for that matter, as a binary fraction of any finite length). Thus, the value that is being passed in to the constructor is not exactly equal to 0.1, appearances notwithstanding.</blockquote>

<p>Instead, you should use <code>BigDecimal.valueOf</code>, which uses a string under the covers to eliminate floating point rounding errors.</p>

<h2>Noncompliant Code Example</h2>
<pre>
double d = 1.1;

BigDecimal bd1 = new BigDecimal(d); // Noncompliant; see comment above
BigDecimal bd2 = new BigDecimal(1.1); // Noncompliant; same result
</pre>

<h2>Compliant Solution</h2>

<pre>
double d = 1.1;

BigDecimal bd1 = BigDecimal.valueOf(d);
BigDecimal bd2 = BigDecimal.valueOf(1.1);
</pre>

--------



## 721.


*  "hashCode" and "toString" should not be called on array instances

system_tags : bug, priority : 3; plugin_rule_key : S2116

While <code>hashCode</code> and <code>toString</code> are available on arrays, they are largely useless. <code>hashCode</code> returns the array's "identity hash code", and <code>toString</code> returns nearly the same value. Neither method's output actually reflects the array's contents. Instead, you should pass the array to the relevant static <code>Arrays</code> method.

<h2>Noncompliant Code Example</h2>
<pre>
public static void main( String[] args )
{
    String argStr = args.toString(); // Noncompliant
    int argHash = args.hashCode(); // Noncompliant

</pre>

<h2>Compliant Solution</h2>
<pre>
public static void main( String[] args )
{
    String argStr = Arrays.toString(args);
    int argHash = Arrays.hashCode(args);

</pre>

--------



## 722.


*  Collections should not be passed as arguments to their own methods

system_tags : bug, priority : 3; plugin_rule_key : S2114

<h5>Passing a collection as an argument to the collection's own method is either an error - some other argument was intended - or simply nonsensical code.</h5>

<p>Further, because some methods require that the argument remain unmodified during the execution, passing a collection to itself can result in undefined behavior.</p>

<h2>Noncompliant Code Example</h2>
<pre>
List &lt;Object&gt; objs = new ArrayList&lt;Object&gt;();
  objs.add("Hello");

  objs.add(objs); // Noncompliant; StackOverflowException if objs.hashCode() called
  objs.addAll(objs); // Noncompliant; behavior undefined
  objs.containsAll(objs); // Noncompliant; always true
  objs.removeAll(objs); // Noncompliant; confusing. Use clear() instead
  objs.retainAll(objs); // Noncompliant; NOOP
</pre>

--------



## 723.


*  Strings literals should be placed on the left side when checking for equality

system_tags : null, priority : 2; plugin_rule_key : S1132

<h5>
It is preferable to place string literals on the left-hand side of an <code>equals()</code> or <code>equalsIgnoreCase()</code> method call.
This prevents null pointer exceptions from being raised, as a string literal can never be null by definition.
</h5>

<p>The following code:</p>

<pre>
String myString = null;

System.out.println("Equal? " + myString.equals("foo"));                        // Non-Compliant - will raise a NPE
System.out.println("Equal? " + (myString != null && myString.equals("foo")));  // Non-Compliant - null check could be removed
</pre>

<p>should be refactored into:</p>

<pre>
System.out.println("Equal?" + "foo".equals(myString));                         // Compliant - properly deals with the null case
</pre>

--------



## 724.


*  Methods should not have too many parameters

system_tags : brain-overload, priority : 2; plugin_rule_key : S00107

<h5>
A long parameter list can indicate that a new structure should be created to wrap the numerous parameters or that the method is doing too many things.
</h5>

--------



## 725.


*  "javax.crypto.NullCipher" should not be used for anything other than testing

system_tags : cwe,owasp-top10,security, priority : 4; plugin_rule_key : S2258

By contract, the <code>NullCipher</code> class provides an "identity cipher" -- one that does not transform or encrypt the plaintext in any way. As a consequence, the ciphertext is identical to the plaintext. So this class should be used for testing, and never in production code. 

<h2>Noncompliant Code Example</h2>
<pre>
NullCipher nc = new NullCipher();
</pre>

<h2>See</h2>
<ul>
	<li><a href="http://cwe.mitre.org/data/definitions/327.html">CWE-327</a>: Use of a Broken or Risky Cryptographic Algorithm</li>
	<li><a href="https://www.owasp.org/index.php/Top_10_2013-A6-Sensitive_Data_Exposure">OWASP Top Ten 2013 Category A6 - Sensitive Data Exposure</a></li>
</ul>

--------



## 726.


*  Deprecated code should be removed eventually

system_tags : null, priority : 0; plugin_rule_key : S1133

<h5>
This rule is meant to be used as a way to track code which is marked as being deprecated.
Deprecated code should eventually be removed.
</h5>

<p>
The following code illustrates this rule:
</p>

<pre>
class Foo {
  /**
    * @deprecated
    */
  public void foo() {    // Non-Compliant
  }

  @Deprecated            // Non-Compliant
  public void bar() {
  }

  public void baz() {    // Compliant
  }
}
</pre>

--------



## 727.


*  Nested blocks of code should not be left empty

system_tags : bug, priority : 2; plugin_rule_key : S00108

<h5>
Most of the time a block of code is empty when a piece of code is really missing.
So such empty block must be either filled or removed.
When a block contains a comment, this block is not considered to be empty.
</h5>

<p>The following code snippet illustrates this rule:</p>

<pre>
void doSomething() {
  for (int i = 0; i < 42; i++)        // Non-Compliant
  {
  }
  for (int i = 0; i < 42; i++);       // Compliant

  if (myVar == 4)                     // Compliant - contains a comment
  {
    // Do nothing because of X and Y
  }
  else                                // Compliant
  {
    doSomething();
  }

  try                                 // Non-Compliant
  {
  }
  catch (Exception e)                 // Compliant
  {
    // Ignore
  }
}
</pre>

--------



## 728.


*  Lines of code should not be too long

system_tags : convention, priority : 1; plugin_rule_key : S00103

<h5>
Having to scroll horizontally makes it harder to get a quick overview and understanding of any piece of code.
</h5>

--------



## 729.


*  "HttpServletRequest.getRequestedSessionId()" should only be used by servlet containers

system_tags : owasp-top10,security, priority : 3; plugin_rule_key : S2254

<h5>According to the Oracle Java API, the <code>HttpServletRequest.getRequestedSessionId()</code> method:</h5>
<blockquote>
Returns the session ID specified by the client. This may not be the same as the ID of the current valid session for this request. If the client did not specify a session ID, this method returns null.
</blockquote>

<p>The session ID it returns is either transmitted in a cookie or a URL parameter so by definition, nothing prevents the end-user from manually updating the value of this session ID in the HTTP request.</p>

<p>Here is an example of a updated HTTP header:</p>
<pre>
GET /pageSomeWhere HTTP/1.1
Host: webSite.com
User-Agent: Mozilla/5.0
Cookie: JSESSIONID=Hacked_Session_Value'''">
</pre>

<p>Due to the ability of the end-user to manually change the value, the session ID in the request should only be used by a servlet container (E.G. Tomcat or Jetty) to see if the value matches the ID of an an existing session. If it does not, the user should be considered  unauthenticated. Moreover, this session ID should never be logged to prevent hijacking of active sessions.</p>

<h2>Noncompliant Code Example</h2>

<pre>
if(isActiveSession(request.getRequestedSessionId()) ){
...
}
</pre>

<h2>See</h2>
    <ul>
      <li><a href="https://www.owasp.org/index.php/Top_10_2013-A2-Broken_Authentication_and_Session_Management">OWASP Top Ten 2013 Category A2 - Broken Authentication and Session Management</a></li>
    </ul>

--------



## 730.


*  Disallowed methods should not be used

system_tags : null, priority : 2; plugin_rule_key : S2253

<h5>This rule allows banning certain methods.</h5>

<p>Given parameters:</p>
    <ul>
      <li>className:java.lang.String</li>
      <li>methodName: replace</li>
      <li>argumentTypes: java.lang.CharSequence, java.lang.CharSequence</li>
    </ul>
<h2>Noncompliant Code Example</h2>
<pre>
String name;
name.replace("A","a");  // Noncompliant
</pre>

--------



## 731.


*  FIXME tags should be handled

system_tags : null, priority : 2; plugin_rule_key : S1134

<h5>
<code>FIXME</code> tags are commonly used to mark places where a bug is suspected, but which the developer wants to deal with later.
Sometimes the developer will not have the time or will simply forget to get back to that tag.
This rule is meant to track those tags, and ensure that they do not go unnoticed.
</h5>

<p>The following code illustrates this rule:</p>

<pre>
int divide(int numerator, int denominator) {
  return numerator / denominator;              // FIXME denominator = 0, Non-Compliant
}
</pre>

--------



## 732.


*  Tabulation characters should not be used

system_tags : convention, priority : 1; plugin_rule_key : S00105

<h5>
Developers should not need to configure the tab width of their text editors in order to be able to read source code.
So the use of tabulation character must be banned.
</h5>

--------



## 733.


*  Loop conditions should be true at least once

system_tags : bug, priority : 3; plugin_rule_key : S2252

If a <code>for</code> loop's condition is false before the first loop iteration, the loop will never be executed. Such loops are almost always bugs, particularly when the initial value and stop conditions are hard-coded.

<h2>Noncompliant Code Example</h2>
<pre>
for (int i = 10; i &lt; 10; i++) {  // Noncompliant 
  // ...
</pre>

--------



## 734.


*  TODO tags should be handled

system_tags : null, priority : 0; plugin_rule_key : S1135

<h5>
<code>TODO</code> tags are commonly used to mark places where some more code is required, but which the developer wants to implement later.
Sometimes the developer will not have the time or will simply forget to get back to that tag.
This rule is meant to track those tags, and ensure that they do not go unnoticed.
</h5>

<p>The following code illustrates this rule:</p>

<pre>
void doSomething() {
  // TODO
}
</pre>

--------



## 735.


*  Files should not have too many lines

system_tags : brain-overload, priority : 2; plugin_rule_key : S00104

<h5>
A source file that grows too much tends to aggregate too many responsibilities and inevitably becomes harder to understand and therefore to maintain.
Above a specific threshold, it is strongly advised to refactor it into smaller pieces of code which focus on well defined tasks.
Those smaller files will not only be easier to understand but also probably easier to test.
</h5>

--------



## 736.


*  Statements should be on separate lines

system_tags : convention, priority : 2; plugin_rule_key : S00122

<h5>
For better readability, do not put more than one statement on a single line.
</h5>

<p>
The following code snippet illustrates this rule:
</p>
<pre>
a = "something"; b = "somethingElse"; // Non-Compliant
c = "anotherThing"; // Compliant
</pre>

--------



## 737.


*  Package names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00120

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate. This rule allows to check that all package names match a provided regular expression.
</h5>

<p>
The following code snippet illustrates this rule when the regular expression value is "^[a-z]+(\\.[a-z][a-z0-9]*)*$":
</p>
<pre>
package org.Example; // Non-Compliant

package org.example; // Compliant
</pre>

--------



## 738.


*  Reflection should not be used to check non-runtime annotations

system_tags : bug, priority : 4; plugin_rule_key : S2109

<h5>The writer of an annotation can set one of three retention policies for it:</h5>
<ul>
  <li><code>RetentionPolicy.SOURCE</code> - these annotations are dropped during compilation, E.G. <code>@Override</code>, <code>@SuppressWarnings</code>.</li>
  <li><code>RetentionPolicy.CLASS</code> - these annotations are present in a compiled class but not loaded into the JVM at runtime. This is the default.</li>
  <li><code>RetentionPolicy.RUNTIME</code> - these annotations are present in the class file and loaded into the JVM.</li>
</ul>
<p>Only annotations that have been given a <code>RUNTIME</code> retention policy will be available to reflection. Testing for annotations with any other retention policy is simply
  an error, since the test will always return false.</p>

<p>This rule checks that reflection is not used to detect annotations that do not have <code>RUNTIME</code> retention.</p>

<h2>Noncompliant Code Example</h2>
<pre>
Method m = String.class.getMethod("getBytes", new Class[] {int.class,
int.class, byte[].class, int.class});
if (m.isAnnotationPresent(Override.class)) {  // Noncompliant; test will always return false, even when @Override is present in the code
</pre>

--------



## 739.


*  if/else/for/while/do statements should always use curly braces

system_tags : convention, priority : 2; plugin_rule_key : S00121

<h5>
Not using curly braces could be error-prone in some cases. For instance in the following example, the two statements seems to be attached to the if statement whereas this is the case only for the first one:
</h5>
<pre>
if (condition) // Non-Compliant
  executeSomething();
  checkSomething();

if (condition) { // Compliant
  executeSomething();
}
checkSomething();
</pre>

--------



## 740.


*  Avoid cycle between java packages

system_tags : null, priority : 2; plugin_rule_key : CycleBetweenPackages

<h5>
When several packages are involved in a cycle (package A > package B > package C > package A where ">" means "depends upon"),
that means that those packages are highly coupled and that there is no way to reuse/extract one of those packages without importing all the other packages.
Such cycle could quickly increase the effort required to maintain an application and to embrace business change.
SonarQube not only detect cycles between packages but also determines what is the minimum effort to break those cycles.
This rule logs an issue on each source file having an outgoing dependency to be cut in order to break a cycle.
</h5>

--------



## 741.


*  Synchronized classes Vector, Hashtable, Stack and StringBuffer should not be used

system_tags : null, priority : 2; plugin_rule_key : S1149

<h5>
Early classes of the Java API, such as <code>Vector</code>, <code>Hashtable</code> and <code>StringBuffer</code>, were synchronized to make them thread-safe.
Unfortunately, synchronization has a big negative impact on performance, even when using these collections from a single thread.
</h5>

<p>It is better to use their new unsynchronized replacements:</p>

<ul>
  <li><code>ArrayList</code> or <code>LinkedList</code> instead of <code>Vector</code></li>
  <li><code>Deque</code> instead of <code>Stack</code></li>
  <li><code>HashMap</code> instead of <code>Hashtable</code></li>
  <li><code>StringBuilder</code> instead of <code>StringBuffer</code></li>
</ul>

<h2>Noncompliant Code Example</h2>

<pre>
Vector cats = new Vector();
</pre>

<h2>Compliant Solution</h2>

<pre>
ArrayList cats = new ArrayList(); 
</pre>

<h2>Exceptions</h2>

<p>Use of those synchronized classes is allowed in method signatures when overriding an existing method.</p>

<pre>
@Override
public Vector getCats() {...} 
</pre>

--------



## 742.


*  Floating point numbers should not be tested for equality

system_tags : bug,misra, priority : 3; plugin_rule_key : S1244

<h5>Floating point math is imprecise because of the challenges of storing such values in a binary representation. Even worse, floating point math is not associative; push a <code>float</code> or a <code>double</code> through a series of simple mathematical operations and the answer will be different based on the order of those operation because of the rounding that takes place at each step.</h5>

<p>Even simple floating point assignments are not simple:</p>
<pre>
float f = 0.1; // 0.100000001490116119384765625
double d = 0.1; // 0.1000000000000000055511151231257827021181583404541015625
</pre>
<p>(Results will vary based on compiler and compiler settings);</p>

<p>Therefore, the use of the equality (<code>==</code>) and inequality (<code>!=</code>) operators on <code>float</code> or <code>double</code> values is almost always an error. Instead the best course is to avoid floating point comparisons altogether. When that is not possible, you should consider using one of Java's float-handling <code>Numbers</code> such as <code>BigDecimal</code> which can properly handle floating point comparisons. A third option is to look not for equality but for whether the value is close enough. I.e. compare the absolute value of the difference between the stored value and the expected value against a margin of acceptable error. Note that this does not cover all cases (<code>NaN</code> and <code>Infinity</code> for instance).</p>

<p>This rule checks for the use of direct and indirect equality/inequailty tests on floats and doubles.</p>

<h2>Noncompliant Code Example</h2>
<pre>
float myNumber = 3.146;
if ( myNumber == 3.146f ) { //Noncompliant. Because of floating point imprecision, this will be false
  // ...
}
if ( myNumber != 3.146f ) { //Noncompliant. Because of floating point imprecision, this will be true
  // ...
}

if (myNumber < 4 || myNumber > 4) { // Noncompliant indirect inequality test
  // ...
}

float zeroFloat = 0.0f;
if(zeroFloat == 0) { //Noncompliant any computation on your float can end up to a value close to, but not equal to, zero.
}
</pre>

<h2>Compliant Solution</h2>
<pre>
float zeroFloat = 0.0f;
if(Float.floatToRawIntBits(zeroFloat) == 0) { //compliant getting back to bit comparison it is ensured we compare zero values
}
</pre>

<h2>Exceptions</h2>
<p>Since <code>NaN</code> is not equal to itself, the specific case of testing a floating point value against itself is a valid test for <code>NaN</code> and is therefore ignored.</p>

<pre>
float f;
double d;
if(f != f) { // Compliant; test for NaN value
  System.out.println("f is NaN");
} else if (f != d) { // Noncompliant
  // ...
}
</pre>

<h2>See</h2>
    <ul>
      <li>MISRA C:2004, 13.3</li>
      <li>MISRA C++:2008, 6-2-2</li>
    </ul>

--------



## 743.


*  Left curly braces should be located at the end of lines of code

system_tags : convention, priority : 2; plugin_rule_key : LeftCurlyBraceEndLineCheck

<h5>
Sharing some coding conventions is a key point to make it possible for a team to efficiently collaborate.
This rule make it mandatory to place left curly braces at the end of lines of code.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
public void myMethod() {              // Compliant
  if(something)
  {                                   // Non-Compliant
    executeTask();
  } else {                            // Compliant
    doSomethingElse();
  }
  if( param1 && param2 && param3
    && something3 && something4)
  {                                   // Non-Compliant
    executeAnotherTask();
  }
}
</pre>

--------



## 744.


*  Try-catch blocks should not be nested

system_tags : null, priority : 2; plugin_rule_key : S1141

<h5>
Nesting <code>try-catch</code> blocks severely impacts the readability of source code because it makes it to difficult to understand which block will catch which exception.
</h5>

<p>The following code:</p>

<pre>
try {
  try {                                     // Non-Compliant
    doSomething();
  } catch (RuntimeException e) {
    /* Ignore */
  }

  doSomethingElse();
} catch (Exception e) {
  /* ... */
}
</pre>

<p>should be refactored into:</p>

<pre>
try {
  dedicatedMethod();                        // Compliant
  doSomethingElse();
} catch (Exception e) {
  /* ... */
}

/* ... */

private void dedicatedMethod() {
  try {                                     // Compliant
    doSomething();
  } catch (RuntimeException e) {
    /* Ignore */
  }
}
</pre>

--------



## 745.


*  Methods should not contain too many return statements

system_tags : brain-overload, priority : 2; plugin_rule_key : S1142

<h5>
Having too many return statements in a method increases the method's essential complexity because the flow of execution is broken each time a return statement is encountered.
This makes it harder to read and understand the logic of the method.
</h5>

<p>
The following code snippet illustrates this rule with the default threshold of 3:
</p>

<pre>
public boolean myMethod() { // Non-Compliant as there are 4 return statements
  if (condition1) {
    return true;
  } else {
    if (condition2) {
      return false;
    } else {
      return true;
    }
  }
  return false;
}
</pre>

--------



## 746.


*  Type parameter names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00119

<h5>Shared naming conventions make it possible for a team to collaborate efficiently. Following the established convention of single-letter type parameter names helps users and maintainers of your code quickly see the difference between a type parameter and a poorly named class.</h5>

<p>This rule check that all type parameter names match a provided regular expression. The following code snippets use the default regular expression.</p>

<h2>Noncompliant Code Example</h2>
<pre>
public class MyClass&lt;TYPE&gt; { // Non-Compliant
  &lt;TYPE&gt; void method(TYPE t) { // Non-compliant
  }
}
</pre>
<h2>Compliant Solution</h2>
<pre>
public class MyClass&lt;T&gt; {
  &lt;T&gt; void method(T t) {
  }
}
</pre>

--------



## 747.


*  Pseudorandom number generators (PRNGs) should not be used in secure context

system_tags : cert,cwe,sans-top25-2011,security, priority : 3; plugin_rule_key : S2245

<h5>When software generates predictable values in a context requiring unpredictability, it may be possible for an attacker to guess the next value that will be generated, and use this guess to impersonate another user or access sensitive information.</h5>

<p>As the <code>java.util.Random</code> class relies on a pseudorandom number generator, this class and relating <code>java.lang.Math.random()</code> method should not be used for security-critical applications or for protecting sensitive data. In such context, the <code>java.security.SecureRandom</code> class which relies on a cryptographically strong random number generator (RNG) should be used in place.</p>

<h2>Noncompliant Code Example</h2>
<pre>
Random random = new Random();
byte bytes[] = new byte[20];
random.nextBytes(bytes);
</pre>

<h2>Compliant solution</h2>
<pre>
SecureRandom random = new SecureRandom();
byte bytes[] = new byte[20];
random.nextBytes(bytes);
</pre>

<h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/338.html">MITRE, CWE-338</a> - Use of Cryptographically Weak Pseudo-Random Number Generator (PRNG)</li>
      <li><a href="http://cwe.mitre.org/data/definitions/330.html">MITRE, CWE-330</a> - Use of Insufficiently Random Values</li>
      <li><a href="https://www.securecoding.cert.org/confluence/display/java/MSC02-J.+Generate+strong+random+numbers">CERT, MSC02-J</a> - Generate strong random numbers</li>

    </ul>

--------



## 748.


*  Return statements should not occur in finally blocks

system_tags : bug, priority : 4; plugin_rule_key : S1143

<h5>
Returning from a <code>finally</code> block suppresses the propagation of any unhandled <code>Throwable</code> which was thrown in the <code>try</code> or <code>catch</code> block.
</h5>

<p>
The following code snippet illustrates this rule.
The developer expects to get "ERROR" in the console whereas "OK" is displayed.
</p>

<pre>
public static void main(String[] args) {
  try {
    doSomethingWhichThrowsException();
    System.out.println("OK");
  } catch (RuntimeException e) {
    System.out.println("ERROR");
  }
}

public static void doSomethingWhichThrowsException() {
  try {
    throw new RuntimeException();
  } finally {
    /* ... */
    return;                                        // Non-Compliant - prevents the RuntimeException from being propagated
  }
}
</pre>

--------



## 749.


*  Abstract class names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00118

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate.
This rule allows to check that all abstract class names match a provided regular expression and non-abstract classes not match.
</h5>

<p>
The following code snippet illustrates this rule when the regular expression value is "^Abstract[A-Z][a-zA-Z0-9]*$":
</p>
<pre>
abstract class MyClass { // Non-Compliant
}

class AbstractLikeClass { // Non-Compliant
}

abstract class AbstractClass { // Compliant
}
</pre>

--------



## 750.


*  Local variable and method parameter names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00117

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate. This rule allows to check that all local variable and method parameter names match a provided regular expression.
</h5>

<p>
The following code snippet illustrates this rule when the regular expression value is "^[a-z][a-zA-Z0-9]*$":
</p>

<pre>
public class MyClass {
  public void method() {
    int FIRST;                      // Non-Compliant
    int second;                     // Compliant
  }

  public void method2(int VALUE) {  // Non-Compliant
  }

  public void method3(int value) {  // Compliant
  }
}
</pre>

--------



## 751.


*  If statement conditions should not always evaluate to "true" or to "false"

system_tags : null, priority : 2; plugin_rule_key : S1145

<h5>
If statements with conditions that are always either true or false are not required, and make the code less readable.
</h5>

<p>The following code:</p>

<pre>
public void myMethod() {
  if (true) {                   // Non-Compliant
    doSomething();
  }
}
</pre>

<p>should be refactored into:</p>

<pre>
public void myMethod() {
  doSomething();                // Compliant
}
</pre>

<p>and the following code:</p>

<pre>
public void myMethod() {
  if (false) {                  // Non-Compliant
    doSomething();
  }
}
</pre>

<p>should be refactored into:</p>

<pre>
public void myMethod() {        // Compliant
}
</pre>

--------



## 752.


*  Field names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00116

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate. This rule allows to check that all field names match a provided regular expression.
</h5>

<p>
The following code snippet illustrates this rule when the regular expression value is "^[a-z][a-zA-Z0-9]*$":
</p>
<pre>
public class MyClass {
  public int FIRST = 1; // Non-Compliant
  public int second = 2; // Compliant
}
</pre>

--------



## 753.


*  Constant names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00115

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate. This rule allows to check that all constant names match a provided regular expression.
</h5>

<p>
The following code snippet illustrates this rule when the regular expression value is "^[A-Z][A-Z0-9]*(_[A-Z0-9]+)*$":
</p>
<pre>
public class MyClass {
  public static final int first = 1; // Non-Compliant
  public static final int SECOND = 2; // Compliant
}

public enum MyEnum {
  first, // Non-Compliant
  SECOND; // Compliant
}
</pre>

--------



## 754.


*  Left curly braces should be located at the beginning of lines of code

system_tags : convention, priority : 2; plugin_rule_key : LeftCurlyBraceStartLineCheck

<h5>
Sharing some coding conventions is a key point to make it possible for a team to efficiently collaborate.
This rule make it mandatory to place left curly braces at the beginning of lines of code.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
public void myMethod
{                                               // Compliant
  if(something)
  {                                             // Compliant
    executeTask();
  } else {                                      // Non-Compliant
    doSomethingElse();
  }
}
</pre>

--------



## 755.


*  System.exit(...) and Runtime.getRuntime().exit(...) should not be called

system_tags : null, priority : 3; plugin_rule_key : S1147

<h5>
Calling <code>System.exit(int status)</code> or <code>Rutime.getRuntime().exit(int status)</code> calls the shutdown hooks and shuts downs the entire Java virtual machine.
  Calling <code>Runtime.getRuntime().halt(int)</code> does an immediate shutdown, without calling the shutdown hooks, and skipping finalization.</h5>

<p>Each of these methods should be used with extreme care, and only when the intent is to stop the whole Java process. For instance, none of them should be called from applications running in a J2EE container.</p>

<h2>Noncompliant Code Example</h2>

<pre>
System.exit(0);
Runtime.getRuntime().exit(0);
  Runtime.getRuntime().halt(0);
</pre>

--------



## 756.


*  Interface names should comply with a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S00114

<h5>
Sharing some naming conventions is a key point to make it possible for a team to efficiently collaborate. This rule allows to check that all interface names match a provided regular expression.
</h5>

<p>
The following code snippet illustrates this rule when the regular expression value is "^[A-Z][a-zA-Z0-9]*$":
</p>
<pre>
public interface MyFirstInterface {...} // Compliant
public interface mySecondInterface {...} // Non-Compliant
</pre>

--------



## 757.


*  Throwable.printStackTrace(...) should never be called

system_tags : error-handling, priority : 3; plugin_rule_key : S1148

<h5>
<code>Throwable.printStackTrace(...)</code> prints a throwable and its stack trace to some stream.
</h5>

<p>Loggers should be used instead to print throwables, as they have many advantages:</p>
<ul>
  <li>Users are able to easily retrieve the logs.</li>
  <li>The format of log messages is uniform and allow users to browse the logs easily.</li>
</ul>

<p>The following code:</p>

<pre>
try {
  /* ... */
} catch(Exception e) {
  e.printStackTrace();        // Non-Compliant
}
</pre>

<p>should be refactored into:</p>

<pre>
try {
  /* ... */
} catch(Exception e) {
  LOGGER.log("context", e);   // Compliant
}
</pre>

--------



## 758.


*  Files should contain an empty new line at the end

system_tags : convention, priority : 1; plugin_rule_key : S00113

<h5>
Some tools such as Git work better when files end with an empty line.
This rule simply generates an issue if it is missing.
</h5>

<p>For example, a Git diff look like:</p>

<pre>
+class Test {
+}
\ No newline at end of file
</pre>

<p>if the empty line is missing at the end of the file.</p>

--------



## 759.


*  Execution of the Garbage Collector should be triggered only by the JVM

system_tags : bug, priority : 3; plugin_rule_key : S1215

<h5>
Calling <code>System.gc()</code> or <code>Runtime.getRuntime().gc()</code> is a bad idea for a simple reason:
there is no way to know exactly what will be done under the hood by the JVM because the behavior will depend on its vendor, version and options:
</h5>

<ul>
  <li>Will the whole application be frozen during the call?</li>
  <li>Is the -XX:DisableExplicitGC option activated?</li>
  <li>Will the JVM simply ignore the call?</li>
  <li>...</li>
</ul>

<p>An application relying on those unpredictable methods is also unpredictable and therefore broken.</p>

<p>The task of running the garbage collector should be left exclusively to the JVM.</p>

--------



## 760.


*  Thread.run() and Runnable.run() should not be called directly

system_tags : multi-threading, priority : 3; plugin_rule_key : S1217

<h5>
The purpose of the <code>Thread.run()</code> and <code>Runnable.run()</code> methods is to execute code in a separate, dedicated thread.
Calling those methods directly doesn't make sense because it causes their code to be executed in the current thread.
</h5>

<p>To get the expected behavior, call the <code>Thread.start()</code> method instead.</p>

<h2>Noncompliant Code Example</h2>
<pre>
Thread myThread = new Thread(runnable);
myThread.run(); // Noncompliant
</pre>

<h2>Compliant Solution</h2>
<pre>
Thread myThread = new Thread(runnable);
myThread.start(); // Compliant
</pre>

--------



## 761.


*  "switch" statements should not contain non-case labels

system_tags : null, priority : 3; plugin_rule_key : S1219

<h5>Even if it is legal, mixing case and non-case labels in the body of a <code>switch</code> statement is very confusing, and can even be the result of a typing error.</h5>

<h2>Noncompliant Code Example</h2>
<p>Case 1, the code is syntactically correct but the behaviour is not the expected one</p>
<pre>
switch (day) {
  case MONDAY:
  case TUESDAY:
  WEDNESDAY:   //instead of "case WEDNESDAY"
    doSomething();
    break;
  ...
}
</pre>
<p>Case 2, the code is correct and behaves as expected but is hardly readable</p>
<pre>
switch (day) {
  case MONDAY:
    break;
  case TUESDAY:
    foo:for(int i = 0 ; i < X ; i++) {
         /* ... */
        break foo;  //This break statement doesn't relate to the nesting case TUESDAY
         /* ... */
    }
    break;
    /* ... */
}
</pre>

<h2>Compliant Solution</h2>

<p>Case 1</p>
<pre>
switch (day) {
  case MONDAY:
  case TUESDAY:
  case WEDNESDAY:
    doSomething();
    break;
  ...
}
</pre>
<p>Case 2</p>
<pre>
switch (day) {
  case MONDAY:
    break;
  case TUESDAY:
    compute(args); //Put the content of the labelled "for" statement in a dedicated method
    break;

    /* ... */
}
</pre>

--------



## 762.


*  "equals(Object obj)" should be overridden along with the "compareTo(T obj)" method

system_tags : bug, priority : 3; plugin_rule_key : S1210

<h5>
According to the Java <code>Comparable.compareTo(T o)</code> documentation:
</h5>

<blockquote>
It is strongly recommended, but not strictly required that <code>(x.compareTo(y)==0) == (x.equals(y))</code>.
Generally speaking, any class that implements the Comparable interface and violates this condition should clearly indicate this fact.
The recommended language is "Note: this class has a natural ordering that is inconsistent with equals."
</blockquote>

<p>
If this rule is violated, weird and unpredictable failures can occur.
For example, in Java 5 the <code>PriorityQueue.remove()</code> method relied on <code>compareTo()</code>, but since Java 6 it relies on <code>equals()</code>.
</p>

<h2>Noncompliant Code Example</h2>

<pre>
public class Foo implements Comparable&lt;Foo&gt; {
  @Override
  public int compareTo(Foo foo) { /* ... */ }      // Noncompliant as the equals(Object obj) method is not overridden
}
</pre>

<h2>Compliant Solution</h2>

<pre>
public class Foo implements Comparable&lt;Foo&gt; {
  @Override
  public int compareTo(Foo foo) { /* ... */ }      // Compliant

  @Override
  public boolean equals(Object obj) { /* ... */ }
}
</pre>

--------



## 763.


*  Constants should not be defined in interfaces

system_tags : null, priority : 1; plugin_rule_key : S1214

<h5>According to Joshua Bloch, author of "Effective Java":</h5>

<blockquote>
<p>
The constant interface pattern is a poor use of interfaces.
</p>

<p>
That a class uses some constants internally is an implementation detail.
Implementing a constant interface causes this implementation detail to leak into the class's exported API.
It is of no consequence to the users of a class that the class implements a constant interface.
In fact, it may even confuse them.
Worse, it represents a commitment:
if in a future release the class is modified so that it no longer needs to use the constants,
it still must implement the interface to ensure binary compatibility.
If a nonfinal class implements a constant interface,
all of its subclasses will have their namespaces polluted by the constants in the interface.
</p>
</blockquote>

<h2>Noncompliant Code Example</h2>

<pre>
interface Status {                      // Non-Compliant
   int OPEN = 1;
   int CLOSED = 2;
}
</pre>

<h2>Compliant Solution</h2>

<pre>
public enum Status {                    // Compliant
  OPEN,
  CLOSED;
}
</pre>

<p>or</p>

<pre>
public final class Status {             // Compliant
   public static final int OPEN = 1;
   public static final int CLOSED = 2;
}
</pre>

--------



## 764.


*  @FunctionalInterface annotation should be used to flag Single Abstract Method interfaces

system_tags : java8, priority : 2; plugin_rule_key : S1609

<h5>A Single Abstract Method (SAM) interface is a Java interface containing only one method. The Java API is full of SAM interfaces, such as java.lang.Runnable, java.awt.event.ActionListener, java.util.Comparator and java.util.concurrent.Callable. SAM interfaces have a special place in Java 8 because they can be implemented using Lambda expressions or Method references.</h5>

<p>Using <code>@FunctionalInterface</code> forces a compile break when an additional, non-overriding abstract method is added to a SAM, which would break the use of Lambda implementations.</p>

<h2>Noncompliant Code Example</h2>
<pre>
  public interface Changeable&lt;T&gt; {
    public void change(T o);
  }
</pre>

<h2>Compliant Solution</h2>
<pre>
  @FunctionalInterface
  public interface Changeable&lt;T&gt; {
    public void change(T o);
  }
</pre>

--------



## 765.


*  The members of an interface declaration or class should appear in a pre-defined order

system_tags : convention, priority : 1; plugin_rule_key : S1213

<h5>
According to the Java Code Conventions as defined by Oracle, the parts of a class or interface declaration should appear in the following order in the source files:
<ul>
<li>Class and instance variables</li>
<li>Constructors</li>
<li>Methods</li>
</ul>
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public class Foo {
  private int field = 0;
  isTrue() {...}
  public Foo() {...}                // Noncompliant, constructor defined after method
  public static final int OPEN = 4; // Noncompliant, variable defined after method
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class Foo{  // Compliant
  public static final int OPEN = 4;
  private int field = 0;
  public Foo() {...}
  public boolean isTrue() {...}
}
</pre>

--------



## 766.


*  The Object.finalize() method should never be called

system_tags : pitfall, priority : 3; plugin_rule_key : ObjectFinalizeCheck

<h5>
According to the official Java documentation, <code>Object.finalize()</code> is called by the garbage collector on an object when garbage collection determines that there are no more references to the object.
Calling this method explicitly breaks this contract and so is misleading.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
public void dispose() throws Throwable {
  this.finalize();                       // Non-Compliant
}
</pre>

--------



## 767.


*  HTTP referers should not be relied on

system_tags : cwe,owasp-top10,security, priority : 3; plugin_rule_key : S2089

<h5>The fields in an HTTP request are putty in the hands of an attacker, and you cannot rely on them to tell you the truth about anything. While it may be safe to store such values after they have been neutralized, decisions should never be made based on their contents.</h5>

<p>This rule flags uses of the referer header field.</p>

<h2>Noncompliant Code Example</h2>
<pre>
public class MyServlet extends HttpServlet {
  protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    String referer = request.getHeader("referer");  // Noncompliant
    if(isTrustedReferer(referer)){
    //..
    }
  //...
  }
}
</pre>

<h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/293">MITRE, CWE-293</a> - Using Referer Field for Authentication</li>
    </ul>

--------



## 768.


*  Parentheses should be removed from a single lambda input parameter when its type is inferred

system_tags : java8, priority : 1; plugin_rule_key : S1611

<h5>There are two possible syntaxes for a lambda having only one input parameter with an inferred type: with and without parentheses around that single parameter. The simpler syntax, without parentheses, is more compact and readable than the one with parentheses, and is therefore preferred.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
(x) -> x * 2
</pre>

<h2>Compliant Solution</h2>
<pre>
x -> x * 2
</pre>

--------



## 769.


*  Replace lambdas with method references when possible

system_tags : java8, priority : 1; plugin_rule_key : S1612

<h5>Method/constructor references are more compact and readable than using lambdas, and are therefore preferred.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
  List<Integer> list = new ArrayList<Integer>();
  list.add(0);
  list.add(1);
  list.add(2);

    list.forEach(n -> { System.out.println(n); });
</pre>

<h2>Compliant Solution</h2>
<pre>
  List<Integer> list = new ArrayList<Integer>();
  list.add(0);
  list.add(1);
  list.add(2);

  list.forEach(System.out::println);
</pre>

--------



## 770.


*  Abstract classes without fields should be converted to interfaces

system_tags : java8, priority : 2; plugin_rule_key : S1610

<h5>With Java 8's "default method" feature, any abstract class without direct or inherited field should be converted into an interface.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public abstract class Car {
  public abstract void start(Environment c);

  public void stop(Environment c) {
    c.freeze(this);
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public interface Car {
  public void start(Environment c);

  public default void stop(Environment c) {
    c.freeze(this);
  }
}
</pre>

--------



## 771.


*  Math operands should be cast before assignment

system_tags : bug, priority : 2; plugin_rule_key : S2184

<h5>When arithmetic is performed on <code>int</code>s, the result will always be an <code>int</code>. You can assign that result to a <code>long</code>, <code>double</code>, or <code>float</code> with automatic type conversion, but having started as an <code>int</code>, the result will likely not be what you expect.</h5>

<p>For instance, if the result of <code>int</code> division is assigned to a floating-point variable, precision will have been lost before the assignment. Likewise, if the result of multiplication is assigned to a <code>long</code>, it may have already overflowed before the assignment.</p>

<p>In either case, the result will not be what was expected. Instead, at least one operand should be cast or promoted to the final type before the operation takes place.</p>

<h2>Noncompliant Code Example</h2>
<pre>
float twoThirds = 2/3; // Noncompliant; int division. Yields 0.0
long millisInYear = 1000*3600*24*365; // Noncompliant; int multiplication. Yields 1471228928
long bigNum = Integer.MAX_VALUE + 2; // Noncompliant. Yields -2147483647
long bigNegNum =  Integer.MIN_VALUE-1; //Noncompliant, gives a positive result instead of a negative one.
Date myDate = new Date(seconds * 1_000); //Noncompliant, won't produce the expected result if seconds > 2_147_483
...
public long compute(int factor){
  return factor * 10_000;  //Noncompliant, won't produce the expected result if factor > 214_748
}
</pre>

<h2>Compliant Solution</h2>
<pre>
float twoThirds = 2f/3; // 2 promoted to float. Yields 0.6666667
long millisInYear = 1000L*3600*24*365; // 1000 promoted to long. Yields 31536000000
long bigNum = Integer.MAX_VALUE + 2L; // 2 promoted to long. Yields 2147483649
long bigNegNum =  Integer.MIN_VALUE-1L; // Yields -2_147_483_649
Date myDate = new Date(seconds * 1_000L);
...
public long compute(int factor){
  return factor * 10_000L;
}
</pre>
or
<pre>
float twoThirds = (float)2/3; // 2 cast to float
long millisInYear = (long)1000*3600*24*365; // 1000 cast to long
long bigNum = (long)Integer.MAX_VALUE + 2;
long bigNegNum =  (long)Integer.MIN_VALUE-1;
Date myDate = new Date((long)seconds * 1_000);
...
public long compute(long factor){
  return factor * 10_000;
}
</pre>

--------



## 772.


*  Empty file

system_tags : null, priority : 2; plugin_rule_key : EmptyFile

<h5>Detect empty files, which do not have any lines of code.</h5>
<p>Example:</p>
<pre>
//package org.foo;
//
//public class Bar {}
</pre>

--------



## 773.


*  Packages should have a javadoc file 'package-info.java'

system_tags : convention, priority : 2; plugin_rule_key : S1228

<h5>Each package in a Java project should include a <code>package-info.java</code> file. The purpose of this file is to document the Java package using javadoc and declare package annotations.</h5>

<h2>Compliant Solution</h2>
<pre>
/**
* This package has non null parameters and is documented.
**/
@ParametersAreNonnullByDefault
package org.foo.bar;
</pre>

--------



## 774.


*  Unused private method

system_tags : unused, priority : 2; plugin_rule_key : UnusedPrivateMethod

<h5>Private methods that are never executed are dead code. Dead code
  means unnecessary, inoperative code that should be removed. This helps
  in maintenance by decreasing the maintained code size, making it easier
  to understand the program and preventing bugs from being introduced.</h5>
<p>In the following two cases, private methods are not considered as
  dead code by SonarQube :</p>
<ul>
  <li>Private empty constructors that are intentionally used to
    prevent any direct instantiation of a class.</li>
  <li>Private methods : readObject(...), writeObject(...),
    writeReplace(...), readResolve(...) which can contractually be used
    when implementing the Serializable interface.</li>
</ul>

--------



## 775.


*  Method parameters, caught exceptions and foreach variables should not be reassigned

system_tags : misra,pitfall, priority : 2; plugin_rule_key : S1226

<h5>
While it is technically correct to assign to parameters from within method bodies, it is better to use temporary variables to store intermediate results.
This rule will typically detect cases where a constructor parameter is assigned to itself instead of a field of the same name, i.e. when <code>this</code> was forgotten.
Allowing parameters to be assigned to also reduces the code readability as developers will not be able to know whether the original parameter or some temporary variable is being accessed without going through the whole method.
Moreover, some developers might also expect assignments of method parameters to be visible from callers, which is not the case and can confuse them.
All parameters should be treated as <code>final</code>.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
class MyClass {
  public String name;

  public MyClass(String name) {
    name = name;                    // Noncompliant - useless identity assignment
  }

  public int add(int a, int b) {
    a = a + b;                      // Noncompliant

    /* additional logic */

    return a;                       // Seems like the parameter is returned as is, what is the point?
  }

  public static void main(String[] args) {
    MyClass foo = new MyClass();
    int a = 40;
    int b = 2;
    foo.add(a, b);                  // Variable "a" will still hold 40 after this call
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
class MyClass {
  public String name;

  public MyClass(String name) {
    this.name = name;               // Compliant
  }

  public int add(int a, int b) {
    return a + b;                   // Compliant
  }

  public static void main(String[] args) {
    MyClass foo = new MyClass();
    int a = 40;
    int b = 2;
    foo.add(a, b);
  }
}
</pre>

--------



## 776.


*  Modulus results should not be checked for direct equality

system_tags : null, priority : 3; plugin_rule_key : S2197

When the modulus of a negative number is calculated, the result will either be negative or zero. Thus, comparing the modulus of a variable for equality with a positive number (or a negative one) could result in false negatives. 

<h2>Noncompliant Code Example</h2>
<pre>
public boolean isOdd(int x) {
  return x % 2 == 1;  // Noncompliant; if x is negative, x % 2 == -1
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public boolean isOdd(int x) {
  return x %2 != 0;
}
</pre>

or

<pre>
public boolean isOdd(int x) {
  return Math.abs(x %2) != 1;
}
</pre>

--------



## 777.


*  Assignments should not be made from within sub-expressions

system_tags : bug,cwe,misra, priority : 2; plugin_rule_key : AssignmentInSubExpressionCheck

<h5>
Assignments within sub-expressions are hard to spot and therefore make the code less readable.
It is also a common mistake to write <code>=</code> when <code>==</code> was meant.
Ideally, expressions should not have side-effects.
</h5>

<h2>Noncompliant Code Example</h2>

<pre>
System.out.println(i = 42);
</pre>

<h2>Compliant Solution</h2>

<pre>
System.out.println(i == 42);
</pre>

<p>or:</p>

<pre>
i = 42;
System.out.println(i);
</pre>

<h2>Exceptions</h2>
<p>Assignments enclosed in relational expressions are allowed.</p>

<pre>
BufferedReader br = new BufferedReader(/* ... */);
String line;
while ((line = br.readLine()) != null) {
  /* ... */
}
</pre>

--------



## 778.


*  Methods should not be named "hashcode"

system_tags : pitfall, priority : 3; plugin_rule_key : S1221

<h5>Naming a method <code>hashcode()</code> is either:</h5>

<ul>
  <li>A bug. Overriding <code>Object.hashCode()</code> was meant and the application does not behave as expected.</li>
  <li>Done on purpose. The name however will confuse every other developer, who will think it is a bug.</li>
</ul>

<p>In both cases, the method should be renamed.</p>

<p>The following code:</p>

<pre>
public int hashcode() { /* ... */ }    // Non-Compliant
</pre>

<p>should be refactored into:</p>

<pre>
@Override
public int hashCode() { /* ... */ }    // Compliant
</pre>

--------



## 779.


*  The default unnamed package should not be used

system_tags : null, priority : 2; plugin_rule_key : S1220

<h5>According to the Java Language Specification:</h5>

<blockquote>
Unnamed packages are provided by the Java platform principally for convenience when developing small or temporary applications or when just beginning development.
</blockquote>

<p>To enforce this best practice, classes located in default package can no longer be access from named ones since Java 1.4.</p>

<p>The following piece of code:</p>

<pre>
public class MyClass { /* ... */ }
</pre>

<p>should be refactored into:</p>

<pre>
package org.example;

public class MyClass{ /* ... */ }
</pre>

--------



## 780.


*  Cookies should be "secure"

system_tags : cwe,owasp-top10,security, priority : 3; plugin_rule_key : S2092

<h5>The "secure" attribute prevents cookies from being sent over plaintext connections such as HTTP, where they would be easily eavesdropped upon. Instead, cookies with the secure attribute are only sent over encrypted HTTPS connections.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
Cookie c = new Cookie(SECRET, secret);  // Noncompliant; cookie is not secure
response.addCookie(c);
</pre>
<h2>Compliant Solution</h2>
<pre>
Cookie c = new Cookie(SECRET, secret);
c.setSecure(true);
response.addCookie(c);
</pre>
<h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/614">MITRE, CWE-614</a> - Sensitive Cookie in HTTPS Session Without 'Secure' Attribute</li>
    </ul>

--------



## 781.


*  Classes should not be empty

system_tags : null, priority : 2; plugin_rule_key : S2094

<h5>There is no good excuse for an empty class. If it's being used simply as a common extension point, it should be replaced with an <code>interface</code>. If it was stubbed in as a placeholder for future development it should be fleshed-out. In any other case, it should be eliminated.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public class Nothing {  // Noncompliant
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public interface Nothing {
}
</pre>

--------



## 782.


*  Non-constructor methods should not have the same name as the enclosing class

system_tags : pitfall, priority : 2; plugin_rule_key : S1223

Having a class and some of its methods sharing the same name is misleading, and leaves others to wonder whether it was done that way on purpose, or was the methods supposed to be a constructor.

<h2>Noncompliant Code Example</h2>
<pre>
class Foo {
  public Foo() {...}
  public int Foo(String label) {...} // Noncompliant
}
</pre>

<h2>Compliant Solution</h2>
<pre>
class Foo {
  public Foo() {...}
  public int foo(String label) {...} // Compliant
}
</pre>

--------



## 783.


*  "main" should not "throw" anything

system_tags : null, priority : 2; plugin_rule_key : S2096

<h5>There's no reason for a <code>main</code> method to <code>throw</code> anything. After all, what's going to catch it?</h5>

<p>Instead, the method should itself gracefully handle any exceptions that may bubble up to it, attach as much contextual information as possible, and perform whatever logging or user communication is necessary.</p>

<h2>Noncompliant Code Example</h2>
<pre>
public static void main(String args[]) throws Exception { // Noncompliant
</pre>

<h2>Compliant Solution</h2>
<pre>
public static void main(String args[]) {
</pre>

--------



## 784.


*  "for" loop incrementers should modify the variable being tested in the loop's stop condition

system_tags : bug, priority : 3; plugin_rule_key : S1994

<h5>It is almost always an error when a <code>for</code> loop's stop condition and incrementer don't act on the same variable. Even when it is not, it could confuse future maintainers of the code, and should be avoided.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
for (i = 0; i < 10; j++) {  // Noncompliant
  // ...
}
</pre>

<h2>Compliant Solution</h2>
<pre>
for (i = 0; i < 10; i++) {
  // ...
}
</pre>

--------



## 785.


*  Throws declarations should not be redundant

system_tags : error-handling, priority : 2; plugin_rule_key : RedundantThrowsDeclarationCheck

<h5>
An exception in a <code>throws</code> declaration in Java is redundant if:
</h5>

<ul>
  <li>It is listed multiple times</li>
  <li>It is a subclass of another listed exception</li>
  <li>It is a <code>RuntimeException</code>, or one of its descendants</li>
</ul>

<p>
The following code:
</p>

<pre>
void foo() throws MyException, MyException {}  // Non-Compliant - should be listed once
void bar() throws Throwable, Exception {}      // Non-Compliant - Exception is a subclass of Throwable
void baz() throws RuntimeException {}          // Non-Compliant - RuntimeException can always be thrown
</pre>

<p>
should be refactored into:
</p>

<pre>
void foo() throws MyException {}               // Compliant
void bar() throws Throwable {}                 // Compliant
void baz() {}                                  // Compliant
</pre>

--------



## 786.


*  Loop counters should not be assigned to from within the loop body

system_tags : bug, priority : 2; plugin_rule_key : ForLoopCounterChangedCheck

<h5>
Loop counters should not be modified in the body of the loop.
However other loop control variables representing logical values may be modified in the loop, for example a flag to indicate that something has been completed, which is then tested in the for statement.
</h5>

<p>
The following code:
</p>

<pre>
String[] names = new String[]{ "Jack", "Jim", null, "John" };
for (int i = 0; i < names.length; i++) {
  if (names[i] == null) {
    i = names.length;                                             // Non-Compliant
  } else {
    System.out.println(names[i]);
  }
}
</pre>

<p>
should be refactored into:
</p>

<pre>
String[] names = new String[]{ "Jack", "Jim", null, "John" };
for (String name: names) {
  if (name == null) {
    break;                                                        // Compliant
  }
  System.out.println(name);
}
</pre>

--------



## 787.


*  Short-circuit logic should be used in boolean contexts

system_tags : bug, priority : 3; plugin_rule_key : S2178

The use of non-short-circuit logic in a boolean context is likely a mistake - one that could cause serious program errors as conditions are evaluated under the wrong circumstances.

<h2>Noncompliant Code Example</h2>
<pre>
if(getTrue() | getFalse()) { ... } // Noncompliant; both sides evaluated
</pre>

<h2>Compliant Solution</h2>
<pre>
if(getTrue() || getFalse()) { ... }  // true short-circuit logic
</pre>

--------



## 788.


*  A field should not duplicate the name of its containing class

system_tags : brain-overload, priority : 2; plugin_rule_key : S1700

<h5>It's confusing to have a class member with the same name (case differences aside) as its enclosing class. This is particularly so when you consider the common practice of naming a class instance for the class itself.</h5>

<p>Best practice dictates that any field or member with the same name as the enclosing class be renamed to be more descriptive of the particular aspect of the class it represents or holds.</p>

<h2>Noncompliant Code Sample</h2>
<pre>
public class Foo {
  private String foo;

  public String getFoo() { }
}

Foo foo = new Foo();
foo.getFoo() // what does this return?
</pre>

<h2>Compliant Solution</h2>
<pre>
public class Foo {
  private String name;

  public String getName() { }
}

//...

Foo foo = new Foo();
foo.getName()
</pre>

<h2>Exception</h2>

<p>When the type of the field is the containing class and that field is static, no issue is raised to allow singletons named like the type.</p>
<pre>
public class Foo {
...
  private static Foo foo;
  public Foo getInstance() {
    if(foo==null){
      foo = new Foo();
    }
    return foo;
  }
...
}
</pre>

--------



## 789.


*  "equals(Object obj)" and "hashCode()" should be overridden in pairs

system_tags : bug, priority : 4; plugin_rule_key : S1206

<h5>According to the Java Language Specification, there is a contract between <code>equals(Object)</code> and <code>hashCode()</code>:</h5>

<blockquote>
If two objects are equal according to the <code>equals(Object)</code> method, then calling the <code>hashCode</code> method on each of the two objects must produce the same integer result.
It is not required that if two objects are unequal according to the <code>equals(java.lang.Object)</code> method, then calling the <code>hashCode</code> method on each of the two objects must produce distinct integer results.
However, the programmer should be aware that producing distinct integer results for unequal objects may improve the performance of hashtables.
</blockquote>

<p>In order to comply with this contract, those methods should be either both inherited, or both overridden.</p>

<h2>Noncompliant Code Example</h2>

<pre>
class MyClass {    // Non-Compliant - should also override "hashCode()"

  @Override
  public boolean equals(Object obj) {
    /* ... */
  }

}
</pre>

<h2>Compliant Solution</h2>

<pre>
class MyClass {    // Compliant

  @Override
  public boolean equals(Object obj) {
    /* ... */
  }

  @Override
  public int hashCode() {
    /* ... */
  }

}
</pre>

--------



## 790.


*  Fields should not duplicate method names

system_tags : brain-overload, priority : 2; plugin_rule_key : S1701

<h5>It's confusing to have a class member with the same name as a method in the class.</h5>

<p>Typically this situation indicates that the method is poorly named; method names should be action-oriented, and thus contain a verb, which is unlikely in the case where both a method and a member have the same name. However, renaming a public method could be disruptive to callers. Therefore renaming the member is the recommended action.</p>

<h2>Noncompliant Code Sample</h2>
<pre>
public class Foo {

  private String query;
  public String query() {
    // do something...
  }

  private void doSomething() {

    String tmp = query; // is this what was intended? Should this have been a call to query()?

  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class Foo {

  private string queryString; // member has been renamed
  public String query() {
    // do something...
  }

  private void doSomething() {

    String tmp = query; // results in a compile error
    String tmp2 = query(); // no question now what was intended
  }
}
</pre>

--------



## 791.


*  Methods named "equals" should override Object.equals(Object)

system_tags : pitfall, priority : 3; plugin_rule_key : S1201

<h5>
"equals" as a method name should be exclusively used to override <code>Object.equals(Object)</code> to prevent any confusion.
</h5>

<p>
It is tempting to overload the method to take a specific class instead of <code>Object</code> as parameter, to save class comparison check.
However, this will not work as expected.
</p>

<p>For example:</p>

<pre>
class MyClass {
  private int foo = 1;

  public boolean equals(MyClass o) {                    // Non-Compliant - "equals" method which does not override Object.equals(Object)
    return o != null && o.foo == this.foo;
  }

  public static void main(String[] args) {
    MyClass o1 = new MyClass();
    Object o2 = new MyClass();
    System.out.println(o1.equals(o2));                  // Will display "false" because "o2" is of type "Object" and not "MyClass"
  }
}
</pre>

<p>should be refactored into:</p>

<pre>
class MyClass {
  private int foo = 1;

  @Override
  public boolean equals(Object o) {                     // Compliant - overrides Object.equals(Object)
    if (o == null || !(o instanceof MyClass)) {
      return false;
    }

    MyClass other = (MyClass)o;
    return this.foo == other.foo;
  }

  /* ... */
}
</pre>

--------



## 792.


*  Classes should not be coupled to too many other classes (Single Responsibility Principle)

system_tags : brain-overload, priority : 2; plugin_rule_key : S1200

<h5>
According to the Single Responsibility Principle, introduced by Robert C. Martin in his book "Principles of Object Oriented Design", a class should have only one responsibility:
</h5>

<blockquote>
If a class has more than one responsibility, then the responsibilities become coupled.
Changes to one responsibility may impair or inhibit the class’ ability to meet the others.
This kind of coupling leads to fragile designs that break in unexpected ways when changed.
</blockquote>

<p>
Classes which rely on many other classes tend to aggregate too many responsibilities and should be split into several smaller ones.
Nested classes dependencies are not counted as dependencies of the outer class.
</p>

<h2>Noncompliant Code Example</h2>

<p>In case the threshold is set to 5</p>
<pre>
class Foo {                        // Noncompliant - Foo depends on too many classes: T1, T2, T3, T4, T5, T6 and T7
  T1 a1;                           // Foo is coupled to T1
  T2 a2;                           // Foo is coupled to T2
  T3 a3;                           // Foo is coupled to T3

  public T4 compute(T5 a, T6 b) {  // Foo is coupled to T4, T5 and T6
    T7 result = a.getResult(b);    // Foo is coupled to T7
    return result;
  }

  public static class Bar {        // Compliant - Bar depends on 2 classes: T8 and T9
    T8 a8;
    T9 a9;
  }
}
</pre>

--------



## 793.


*  Avoid too complex class

system_tags : brain-overload, priority : 2; plugin_rule_key : ClassCyclomaticComplexity

<h5>The Cyclomatic Complexity is measured by the number of (&&, ||)
	operators and (if, while, do, for, ?:, catch, switch, case, return,
	throw) statements in the body of a class plus one for each constructor,
	method (but not getter/setter), static initializer, or instance
	initializer in the class. The last return statement in method, if exists,
	is not taken into account.</h5>
<p>
	Even when the Cyclomatic Complexity of a class is very high, this
	complexity might be well distributed among all methods. Nevertheless,
	most of the time, a very complex class is a class which breaks the <a
		href='http://en.wikipedia.org/wiki/Single_responsibility_principle'>Single
		Responsibility Principle</a> and which should be re-factored to be split
	in several classes.
</p>

--------



## 794.


*  Lamdbas containing only one statement should not nest this statement in a block

system_tags : java8, priority : 2; plugin_rule_key : S1602

<h5>There are two ways to write lambdas that contain single statement, but one is definitely more compact and readable than the other.</h5>
<h2>Noncompliant Code Example</h2>

<pre>
 x -> {System.out.println(x+1);}
(a, b) -> { return a + b; }
</pre>

<h2>Compliant Solution</h2>

<pre>
 x -> System.out.println(x+1)
(a, b) -> a + b
</pre>

--------



## 795.


*  Anonymous inner classes containing only one method should become lambdas

system_tags : java8, priority : 2; plugin_rule_key : S1604

<h5>Before Java 8, the only way to partially support closures in Java was by using anonymous inner classes. But the syntax of anonymous classes may seem unwieldy and unclear.</h5>

<p>With Java 8, most uses of anonymous inner classes should be replaced by lambdas to highly increase the readability of the source code.</p>

<h2>Noncompliant Code Example</h2>
<pre>
myCollection.map(new Mapper<String,String>() {
  public String map(String input) {
    return new StringBuilder(input).reverse().toString();
  }
});
</pre>

<h2>Compliant Solution</h2>
<pre>
myCollection.map(element -> new StringBuilder(element).reverse().toString());
</pre>

--------



## 796.


*  "switch" statements should have at least 3 cases

system_tags : misra, priority : 1; plugin_rule_key : S1301

<h5>
<code>switch</code> statements are useful when there are many different cases depending on the value of the same expression.
For just one or two cases however, the code will be more readable with <code>if</code> statements.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
switch (variable) {
  case 0:
    doSomething();
    break;
  default:
    doSomethingElse();
    break;
}
</pre>

<h2>Compliant Solution</h2>
<pre>
if (variable == 0) {
  doSomething();
} else {
  doSomethingElse();
}
</pre>

--------



## 797.


*  The Object.finalize() method should never be overriden

system_tags : null, priority : 3; plugin_rule_key : ObjectFinalizeOverridenCheck

<h5>
This Object.finalize() method is called by the garbage collector on an object when garbage collection determines that there are no more references to the object.
But there is absolutely no warranty that this method will be called AS SOON AS the last references to the object are removed.
It can be few microseconds to few minutes later.
So when some system resources need to be disposed by an object it's better to not rely on this asynchronous mechanism to dispose them.
</h5>

<p>
The following piece of code illustrates this rule:
</p>

<pre>
public class MyClass {

  protected void finalize() {
    releaseSomeResources();     // Non-Compliant
  }

}
</pre>

--------



## 798.


*  Annotation repetitions should not be wrapped

system_tags : java8, priority : 3; plugin_rule_key : S1710

<h5>Before Java 8 if you needed to use multiple instances of the same annotation, they had to be wrapped in a container annotation. With Java 8, that's no longer necessary, allowing for cleaner, more readable code.</h5>

<h2>Noncompliant Code Sample</h2>
<pre>
@SomeAnnotations({
@SomeAnnotation(..a..),
@SomeAnnotation(..b..),
@SomeAnnotation(..c..),
})
public class SomeClass {
...
}
</pre>

<h2>Compliant Solution</h2>
<pre>
@SomeAnnotation(..a..)
@SomeAnnotation(..b..)
@SomeAnnotation(..c..)
public class SomeClass {
...
}
</pre>

--------



## 799.


*  "instanceof" operators that always return "true" should be removed

system_tags : bug,cwe, priority : 2; plugin_rule_key : S1850

<h5><code>instanceof</code> operators that always return <code>true</code> are either useless or the result of a misunderstanding which could lead to unexpected behavior in production.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public boolean isSuitable(Integer param) {
...
  if(param instanceof Number) {  //Always true as param is an Integer, unless param is null
    doSomething();
  }
...
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public boolean isSuitable(Integer param) {
...
  doSomething();
...
}
</pre>

<h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/571.html">MITRE, CWE-571</a> - Expression is Always True</li>
    </ul>

--------



## 800.


*  NOPMD suppression comment filters should not be used

system_tags : null, priority : 1; plugin_rule_key : S1310

<h5>This rule allows to track usages of this PMD suppression comment filtering mechanism.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
// NOPMD
</pre>

--------



## 801.


*  IP addresses should not be hardcoded

system_tags : security, priority : 2; plugin_rule_key : S1313

<h5>Hardcoding an IP address into source code is a bad idea for several reasons:</h5>

<ul>
  <li>a recompile is required if the address changes</li>
  <li>it forces the same address to be used in every environment (dev, sys, qa, prod)</li>
  <li>it places the responsibility of setting the value to use in production on the shoulders of the developer</li>
</ul>

<h2>Noncompliant Code Example</h2>
<pre>
String ip = "127.0.0.1";
Socket socket = new Socket(ip, 6667);
</pre>

<h2>Compliant Solution</h2>
<pre>
String ip = System.getProperty("myapplication.ip");
Socket socket = new Socket(ip, 6667);
</pre>

--------



## 802.


*  Loggers should be "private static final" and should share a naming convention

system_tags : convention, priority : 2; plugin_rule_key : S1312

<h5>Whatever is the logging framework (logback, log4j, commons-logging, java.util.logging, ...), a logger should be:</h5>

<ul>
  <li><code>private</code>: Never be accessible outside of its parent class. If another class needs to log something, it should instantiate its own logger.</li>
  <li><code>static</code>: Not dependent on an instance of a class (an object). When logging something, contextual information can of course be provided in the messages but the logger should be created at class level to prevent creating a logger along with each object.</li>
  <li><code>final</code>: Be created once and only once per class.</li>
</ul>

<h2>Noncompliant Code Example</h2>
<pre>
public class Foo {
  public Logger logger = LoggerFactory.getLogger(Foo.class);         // Noncompliant

  public void doSomething() {
    /* ... */
  }
}

public class Bar {
  public static void main(String[] args) {
    Foo foo = new Foo();
    foo.logger.info("Program started");
    foo.doSomething();
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class Foo {
  private static final Logger LOGGER = LoggerFactory.getLogger(Foo.class); // Compliant

  public void doSomething() {
    /* ... */
  }
}

public class Bar {
  private static Log LOGGER = LogFactory.getLogger(Bar.class);       // Compliant

  public static void main(String[] args) {
    LOGGER.info("Program started");
    Foo foo = new Foo();
    foo.run();
  }
}
</pre>

--------



## 803.


*  Declarations should use Java collection interfaces such as "List" rather than specific implementation classes such as "LinkedList"

system_tags : null, priority : 2; plugin_rule_key : S1319

<h5>
The purpose of the Java Collections API is to provide a well defined hierarchy of interfaces in order to hide all implementation details.
Implementating classes must be used to instantiate a new collection, but the result of an instantiation should immediately be stored in a variable whose type is a Java Collection interface.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public class Employees {
  private HashSet&lt;Employee&gt; employees = new HashSet&lt;Employee&gt;();  // Noncompliant - "employees" should have type "Set" rather than "HashSet"

  public HashSet&lt;Employee&gt; getEmployees() {                       // Noncompliant
    return employees;
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class Employees {
  private Set&lt;Employee&gt; employees = new HashSet&lt;Employee&gt;();      // Compliant

  public Set&lt;Employee&gt; getEmployees() {                           // Compliant
    return employees;
  }
}
</pre>

--------



## 804.


*  "object == null" should be used instead of "object.equals(null)"

system_tags : null, priority : 3; plugin_rule_key : S1318

<h5>Inexperienced Java developers might expect the <code>Object.equals(Object obj)</code> method to correctly handle the case where the left hand side is null, but that is not the case.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
if (variable.equals(null)) { /* ... */ }   // Noncompliant - "variable" is really null, a NullPointerException is thrown
</pre>

<h2>Compliant Solution</h2>
<pre>
if (variable == null) { /* ... */ }        // Compliant
</pre>

--------



## 805.


*  Generic wildcard types should not be used in return parameters

system_tags : null, priority : 2; plugin_rule_key : S1452

<h5>
  Using a wildcard as a return type implicitly means that the return parameter should be considered as read-only but without any way to enforce this contract.
</h5>
<p>
  Let's take the example of method returning a "List&lt;&#63; extends Animal&gt;". Is it possible on this list to add a Dog, a Cat, ... we simply don't know. The consumer of a method should not have to deal with such disruptive questions.
</p>


<h2>Noncompliant Code Example</h2>
<pre>
List&lt;? extends Animal&gt; getAnimals(){...}
</pre>

<h2>Compliant solution</h2>
<pre>
//First Solution: the list can contain any kind of animals
List&lt;Animal&gt; getAnimals(){...}

//Second Solution: the list can contain only one type of animal
List&lt;E&gt; getAnimals(){...} //Where E extends Animal in the signature of the nesting class
</pre>

--------



## 806.


*  Source code should be correctly indented

system_tags : convention, priority : 2; plugin_rule_key : IndentationCheck

<h5>
Proper indentation is a simple and effective way to improve the code's readability.
Consistent indentation among developers also reduces the differences that are committed to source control systems, making code reviews easier.
</h5>

<p>The following code illustrates this rule with an indentation level of 2:</p>

<pre>
class Foo {
  public int a; // Compliant
public int b;   // Non-Compliant
}
</pre>

--------



## 807.


*  Copyright and license headers should be defined in all source files

system_tags : convention, priority : 4; plugin_rule_key : S1451

<h5>
Each source file should start with a header stating file ownership and the license which must be used to distribute the application.
This rule must be fed with the header text which is expected at the beginning of every file.
</h5>

<p>For example, for SonarSource's open source softwares, the <code>headerFormat</code> property must be set to:</p>
<pre>
/*
 * SonarQube, open source software quality management tool.
 * Copyright (C) 2008-2013 SonarSource
 * mailto:contact AT sonarsource DOT com
 *
 * SonarQube is free software; you can redistribute it and/or
 * modify it under the terms of the GNU Lesser General Public
 * License as published by the Free Software Foundation; either
 * version 3 of the License, or (at your option) any later version.
 *
 * SonarQube is distributed in the hope that it will be useful,
 * but WITHOUT ANY WARRANTY; without even the implied warranty of
 * MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
 * Lesser General Public License for more details.
 *
 * You should have received a copy of the GNU Lesser General Public License
 * along with this program; if not, write to the Free Software Foundation,
 * Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.
 */
</pre>

--------



## 808.


*  CHECKSTYLE:OFF suppression comment filters should not be used

system_tags : null, priority : 1; plugin_rule_key : S1315

<h5>This rule allows to track usages of this Checkstyle suppression comment filtering mechanism.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
// CHECKSTYLE:OFF
</pre>

--------



## 809.


*  Octal values should not be used

system_tags : misra,pitfall, priority : 2; plugin_rule_key : S1314

<h5>
Integer literals starting with a zero are octal rather than decimal values.
While using octal values in Java is fully supported, most developers do not have experience with them.
They may not recognize octal values as such, mistaking them instead for decimal values.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
int myNumber = 010;   // myNumber will hold 8, not 10 - was this really expected?
</pre>

<h2>Compliant Solution</h2>
<pre>
int myNumber = 8;
</pre>

--------



## 810.


*  StringBuilder and StringBuffer should not be instantiated with a character

system_tags : null, priority : 2; plugin_rule_key : S1317

<h5>
  Instantiating a StringBuilder or a StringBuffer with a character is misleading because most Java developers would expect the character to be the initial value of the StringBuffer.
</h5>
<p>
  What actually happens is that the int representation of the character is used to determine the initial size of the StringBuffer.
</p>

<h2>Noncompliant Code Example</h2>

<pre>
StringBuffer foo = new StringBuffer('x');   //equivalent to StringBuffer foo = new StringBuffer(120);
</pre>

<h2>Compliant Solution</h2>

<pre>
StringBuffer foo = new StringBuffer("x");
</pre>

--------



## 811.


*  Synchronisation should not be based on Strings or boxed primitives

system_tags : bug,cert, priority : 4; plugin_rule_key : S1860

Objects which are pooled and potentially reused should not be used for synchronization. If they are, it can cause unrelated threads to deadlock with unhelpful stacktraces. Specifically, <code>String</code> literals, and boxed primitives such as Integers should not be used as lock objects because they are pooled and reused. The story is even worse for <code>Boolean</code> objects, because there are only two instances of <code>Boolean</code>, <code>Boolean.TRUE</code> and <code>Boolean.FALSE</code> and every class that uses a Boolean will be referring to one of the two.

<h2>Noncompliant Code Example</h2>
<pre>
private static final Boolean bLock = Boolean.FALSE;
private static final Integer iLock = Integer.valueOf(0);
private static final String sLock = "LOCK";

public void doSomething() {

  synchronized(bLock) {  // Noncompliant
    // ...
  }
  synchronized(iLock) {  // Noncompliant
    // ...
  }
  synchronized(sLock) {  // Noncompliant
    // ...
  }
</pre>

<h2>Compliant Solution</h2>
<pre>
private static final Object lock1 = new Object();
private static final Object lock2 = new Object();
private static final Object lock3 = new Object();

public void doSomething() {

  synchronized(lock1) {
    // ...
  }
  synchronized(lock2) {
    // ...
  }
  synchronized(lock3) {
    // ...
  }
</pre>

<h2>See</h2>
<a href="https://www.securecoding.cert.org/confluence/x/rQGeAQ">CERT, LCK01-J</a> - Do not synchronize on objects that may be reused

--------



## 812.


*  Conditions in related "if/else if" statements should not be duplicated

system_tags : bug,unused, priority : 3; plugin_rule_key : S1862

<h5>
  A chain of if/else if statements is evaluated from top to bottom. At most, only one branch of the chain will be executed: the first one with a condition that evaluates to true.
</h5>
<p>
  Therefore, duplicating a condition in a sequence of if/else if statements automatically leads to dead code. Usually, is due to a copy/paste error. Obviously it could lead to unexpected behavior.
</p>

<h2>Noncompliant Code Sample</h2>
<pre>
if (param == 1)
  openWindow();
else if (param == 2)
  closeWindow();
else if (param == 1)  // For sure this is a bug
  moveWindowToTheBackground();
</pre>

<h2>Compliant Solution</h2>
<pre>
if (param == 1)
  openWindow();
else if (param == 2)
  closeWindow();
else if (param == 3)
  moveWindowToTheBackground();
</pre>

--------



## 813.


*  Deprecated classes and interfaces should not be extended/implemented

system_tags : cwe,obsolete, priority : 2; plugin_rule_key : S1724

<h5>Deprecated classes and interfaces should be avoided, rather than used, inherited or extended. Deprecation is a warning that the class or interface has been superseded, and will eventually be removed. The deprecation period allows you to make a smooth transition away from the aging, soon-to-be-retired technology.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
/**
* @deprecated  As of release 1.3, replaced by {@link #Fee}
*/@Deprecated
class Foo { ... }

class Bar extends Foo { ... }
</pre>

<h2>Compliant Solution</h2>
<pre>
class Bar extends Fee { ... }
</pre>

<h2>Exception</h2>
<p>When the class that extends a deprecated class is itself deprecated, the extending class will be ignored.</p>
<pre>
@Deprecated
class Bar extends Foo { ... } // compliant Bar is deprecated.
</pre>

  <h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/477.html">MITRE, CWE-477</a> - Use of Obsolete Functions</li>
    </ul>

--------



## 814.


*  Increment (++) and decrement (--) operators should not be mixed with other operators in an expression

system_tags : cert,misra, priority : 2; plugin_rule_key : S881

<h5>
The use of increment and decrement operators in combination with other arithmetic operators is not recommended, because:
It can significantly impair the readability of the code.
It introduces additional side effects into a statement, with the potential for undefined behavior.
It is safer to use these operators in isolation from any other arithmetic operators.
</h5>

<h2>Noncompliant Code Example</h2>

<pre>
u8a = ++u8b + u8c--;
foo = bar++ / 4;
</pre>

<h2>Compliant Solution</h2>
<p>The following sequence is clearer and therefore safer:</p>

<pre>
++u8b;
u8a = u8b + u8c;
u8c--;
foo = bar / 4;
bar++;
</pre>

--------



## 815.


*  Java parser failure

system_tags : null, priority : 2; plugin_rule_key : ParsingError

<h5>
When the Java parser fails, it is possible to record the failure as an issue on the file.
This way, not only it is possible to track the number of files that do not parse but also to easily find out why they do not parse.
</h5>

--------



## 816.


*  Package declaration should match source file directory

system_tags : null, priority : 2; plugin_rule_key : S1598

<h5>By convention, a Java class' physical location (source directories) and its logical representation (packages) should be kept in sync. Thus a Java file located at "src/org/sonarqube/Foo.java" should have a package of "org.sonarqube".</h5>

<p>Unfortunately, this convention is not enforced by Java compilers, and nothing prevents a developer from making the "Foo.java" class part of the "com.apple" package, which could degrade the maintainability of both the class and its application.</p>

--------



## 817.


*  Collections.emptyList(),emptyMap() and emptySet() should be used instead of Collections.EMPTY_LIST, EMPTY_MAP and EMPTY_SET

system_tags : null, priority : 2; plugin_rule_key : S1596

<h5>Since the introduction of generics in Java 5, it is recommenced to use generic types such as <code>List&lt;String&gt;</code> instead of raw ones such as just <code>List</code>. Assigning a raw type into a generic one is not type safe, and will generate a warning. The old <code>EMPTY_...</code> fields of the <code>Collections</code> class return raw types, whereas the newer <code>empty...()</code> methods return generic ones.</h5>

Developers will also more easily find the <code>emptyIterator()</code> and <code>emptyListIterator()</code> methods for which there is no field equivalent if they are used to call the methods.

<h2>Noncompliant Code Example</h2>
<pre>
List&lt;String&gt; collection1 = Collections.EMPTY_LIST;
Map&lt;String, String&gt; collection2 = Collections.EMPTY_MAP;
Set&lt;String&gt; collection3 = Collections.EMPTY_SET;
</pre>

<h2>Compliant Solution</h2>
<pre>
List&lt;String&gt; collection1 = Collections.emptyList();
Map&lt;String, String&gt; collection2 = Collections.emptyMap();
Set&lt;String&gt; collection3 = Collections.emptySet();
</pre>

--------



## 818.


*  Right curly brace and next "else", "catch" and "finally" keywords should be located on the same line

system_tags : convention, priority : 2; plugin_rule_key : RightCurlyBraceSameLineAsNextBlockCheck

<h5>
Sharing some coding conventions is a key point to make it possible for a team to efficiently collaborate.
This rule make it mandatory to place closing curly braces on the same line that next <code>else</code>, <code>catch</code> or <code>finally</code> keywords.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
public void myMethod() {
  if(something) {
    executeTask();
  } else if (somethingElse) {          // Compliant
    doSomethingElse();
  }
  else {                               // Non-Compliant
     generateError();
  }

  try {
    generateOrder();
  } catch (Exception e) {              // Compliant
    log(e);
  }
  finally {                            // Non-Compliant
    closeConnection();
  }
}
</pre>

--------



## 819.


*  Collapsible "if" statements should be merged

system_tags : null, priority : 2; plugin_rule_key : S1066

<h5>Merging collapsible <code>if</code> statements increases the code's readability.</h5>

<h2>Noncompliant Code Example</h2>

<pre>
if (file != null) {
  if (file.isFile() || file.isDirectory()) {
    /* ... */
  }
}
</pre>
<h2>Compliant Solution</h2>

<pre>
if (file != null && isFileOrDirectory(file)) { 
  /* ... */
}

private static boolean isFileOrDirectory(File file) {
  return file.isFile() || file.isDirectory();
}
</pre>

--------



## 820.


*  Expressions should not be too complex

system_tags : brain-overload, priority : 2; plugin_rule_key : S1067

<h5>
The complexity of an expression is defined by the number of <code>&&</code>, <code>||</code> and <code>condition ? ifTrue : ifFalse</code> operators it contains.
A single expression's complexity should not become too high to keep the code readable.
</h5>

<p>The following code, with a maximum complexity of 3:</p>

<pre>
if (condition1 && condition2 && condition3 && condition4) { /* ... */ }  // Non-Compliant
</pre>

<p>could be refactored into something like:</p>

<pre>
if (relevantMethodName1() && relevantMethodName2()) { /* ... */ }        // Compliant

/* ... */

private boolean relevantMethodName1() {
  return condition1 && condition2;
}

private boolean relevantMethodName2() {
  return condition3 && condition4;
}
</pre>

--------



## 821.


*  Methods should not be too complex

system_tags : brain-overload, priority : 2; plugin_rule_key : MethodCyclomaticComplexity

<h5>The Cyclomatic Complexity is measured by the number of
	(&amp;&amp;, ||) operators and (if, while, do, for, ?:, catch, switch,
	case, return, throw) statements in the body of a class plus one for
	each constructor, method (but not getter/setter), static initializer,
	or instance initializer in the class. The last return statement in
	method, if exists, is not taken into account.</h5>
<p>
	Even when the Cyclomatic Complexity of a class is very high, this
	complexity might be well distributed among all methods. Nevertheless,
	most of the time, a very complex class is a class which breaks the <a
		href="http://en.wikipedia.org/wiki/Single_responsibility_principle">Single
		Responsibility Principle</a> and which should be re-factored to be split
	in several classes.
</p>

--------



## 822.


*  Empty statements should be removed

system_tags : null, priority : 2; plugin_rule_key : EmptyStatementUsageCheck

<h5>Empty statements, i.e. <code>;</code>, are usually introduced by mistake, for example because:</h5>

<ul>
  <li>It was meant to be replaced by an actual statement, but this was forgotten.</li>
  <li>There was a typo which lead to the semicolon to be doubled, i.e. <code>;;</code>.</li>
</ul>

<p>Examples:</p>

<pre>
void doSomething() {
  ;                                                       // Non-Compliant - was used as a kind of TODO marker
}
</pre>

<pre>
System.out.println("Hello, world!");;                     // Non-Compliant - double ;
</pre>

<p>Rarely, they are used on purpose, as the body of a loop:</p>

<pre>
for (int i = 0; i < 3; System.out.println(i), i++);       // Non-Compliant
</pre>

<p>It is a bad practice to have side-effects outside of the loop body, and therefore that code should be refactored into:</p>

<pre>
for (int i = 0; i < 3; i ++) {                            // Compliant
  System.out.println(i);
}
</pre>

--------



## 823.


*  Unused labels should be removed

system_tags : misra,unused, priority : 2; plugin_rule_key : S1065

<h5>
  If a label is declared but not used in the program, it can be considered as dead code and should therefore be removed.
  This will improve maintainability as developers will not wonder what this label is used for.
</h5>

<h2>Noncompliant code example</h2>

<pre>
void foo() {
  outer: //label is not used.
  for(int i = 0; i<10; i++) {
    break;
  }
}
</pre>

<h2>See</h2>
<ul>
  <li>MISRA C:2012, 2.6 - A function should not contain unused label declarations</li>
</ul>

--------



## 824.


*  Unused private fields should be removed

system_tags : unused, priority : 2; plugin_rule_key : S1068

<h5>
If a private field is declared but not used in the program, it can be considered dead code and should therefore be removed.
This will improve maintainability because developers will not wonder what the variable is used for.
</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public class MyClass {
  private int foo = 42;

  public int compute(int a) {
    return a * 42;
  }
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class MyClass {
  public int compute(int a) {
    return a * 42;
  }
}
</pre>

<h2>Exceptions</h2>

<p>
The Java serialization runtime associates with each serializable class a version number, called <code>serialVersionUID</code>, which is used during deserialization to verify that the sender and receiver of a serialized object have loaded classes for that object that are compatible with respect to serialization.
A serializable class can declare its own <code>serialVersionUID</code> explicitly by declaring a field named <code>serialVersionUID</code> that must be static, final, and of type long. By definition those <code>serialVersionUID</code> fields should not be reported by this rule:
</p>

<pre>
public class MyClass implements java.io.Serializable {
  private static final long serialVersionUID = 42L;
}
</pre>

--------



## 825.


*  Credentials should not be hard-coded

system_tags : cwe,owasp-top10,sans-top25-2011,security, priority : 3; plugin_rule_key : S2068

<h5>Because it is easy to extract strings from a compiled application, credentials should never be hard-coded. Do so, and they're almost guaranteed to end up in the hands of an attacker. This is particularly true for applications that are distributed.</h5>
<p>Credentials should be stored outside of the code in a strongly-protected encrypted configuration file or database.</p>

<h2>Noncompliant Code Example</h2>
<pre>
Connection conn = null;
try {
  conn = DriverManager.getConnection("jdbc:mysql://localhost/test?" +
        "user=steve&amp;password=blue"); // Noncompliant
  String uname = "steve";
  String password = "blue";
  conn = DriverManager.getConnection("jdbc:mysql://localhost/test?" +
        "user=" + uname + "&amp;password=" + password); // Noncompliant
</pre>

<h2>Compliant Solution</h2>
<pre>
Connection conn = null;
try {
  String uname = getEncryptedUser();
  String password = getEncryptedPass();
  conn = DriverManager.getConnection("jdbc:mysql://localhost/test?" +
        "user=" + uname + "&amp;password=" + password);
</pre>

<h2>See</h2>
<ul>
<li><a href="http://cwe.mitre.org/data/definitions/798">MITRE, CWE-798</a> - Use of Hard-coded Credentials</li>
<li><a href="http://cwe.mitre.org/data/definitions/259">MITRE, CWE-259</a> - Use of Hard-coded Password</li>
</ul>

--------



## 826.


*  Array designators "[]" should be on the type, not the variable

system_tags : convention, priority : 1; plugin_rule_key : S1197

<h5>
Array designators should always be located on the type for better code readability.
Otherwise, developers must look both at the type and the variable name to know whether or not a variable is an array.
</h5>

<p>The following code snippet illustrates this rule:</p>

<pre>
int matrix[][];   // Non-Compliant
int[] matrix[];   // Non-Compliant
int[][] matrix;   // Compliant
</pre>

--------



## 827.


*  "Object.wait(...)" should never be called on objects that implement "java.util.concurrent.locks.Condition"

system_tags : bug,pitfall, priority : 4; plugin_rule_key : S1844

<h5>From the Java API documentation:</h5>
<blockquote>
<code>Condition</code> factors out the <code>Object</code> monitor methods (<code>wait</code>, <code>notify</code> and <code>notifyAll</code>) into distinct objects to give the effect of having multiple wait-sets per object, by combining them with the use of arbitrary Lock implementations. Where a <code>Lock</code> replaces the use of <code>synchronized</code> methods and statements, a <code>Condition</code> replaces the use of the <code>Object</code> monitor methods.
</blockquote>

The purpose of implementing the <code>Condition</code> interface is to gain access to its more nuanced <code>await</code> methods. Therefore, calling the method <code>Object.wait(...)</code> on a class implementing the <code>Condition</code> interface is silly and confusing.

<h2>Noncompliant Code Example</h2>

<pre>
final Lock lock = new ReentrantLock();
final Condition notFull  = lock.newCondition();
...
notFull.wait();
</pre>

<h2>Compliant Solution</h2>
<pre>
final Lock lock = new ReentrantLock();
final Condition notFull  = lock.newCondition();
...
notFull.await();
</pre>

--------



## 828.


*  Nested code blocks should not be used

system_tags : null, priority : 2; plugin_rule_key : S1199

<h5>
Nested code blocks can be used to create a new scope and restrict the visibility of the variables defined within.
Using this feature in a method typically indicates that it takes on too many responsibilities, and should be refactored into smaller ones.
</h5>

<p>The following code:</p>

<pre>
public void evaluate(int operator) {
  switch (operator) {
    /* ... */
    case ADD: {                                // Non-Compliant - nested code block '{' ... '}'
        int a = stack.pop();
        int b = stack.pop();
        int result = a + b;
        stack.push(result);
        break;
      }
    /* ... */
  }
}
</pre>

<p>should be refactored into:</p>

<pre>
public void evaluate(int operator) {
  switch (operator) {
    /* ... */
    case ADD:                                  // Compliant
      evaluateAdd();
      break;
    /* ... */
  }
}

private void evaluateAdd() {
  int a = stack.pop();
  int b = stack.pop();
  int result = a + b;
  stack.push(result);
}
</pre>

--------



## 829.


*  Objects should not be created to be dropped immediately without being used

system_tags : bug, priority : 3; plugin_rule_key : S1848

There is no good reason to create a new object to not do anything with it. Most of the time, this is due to a missing piece of code and so could lead to an unexpected behavior in production.

<h2>Noncompliant Code Example</h2>
<pre>
if (x &lt; 0)
  new IllegalArgumentException("x must be nonnegative");
</pre>

<h2>Compliant Solution</h2>
<pre>
if (x &lt; 0)
  throw new IllegalArgumentException("x must be nonnegative");
</pre>

--------



## 830.


*  SHA-1 and MD5 hash algorithms should not be used

system_tags : cwe,owasp-top10,sans-top25,security, priority : 3; plugin_rule_key : S2070

<h5>The MD5 algorithm and its successor, SHA-1, are no longer considered secure, because it is too easy to create hash collisions with them. That is, it takes too little computational effort to come up with a different input that produces the same MD5 or SHA-1 hash, and using the new, same-hash value gives an attacker the same access as if he had the originally-hashed value.</h5>

<p>This rule tracks usage of the <code>java.security.MessageDigest</code>, and <code>org.apache.commons.codec.digest.DigestUtils</code> classes to instantiate MD5 or SHA-1 algorithms, and of Guava's <code>com.google.common.hash.Hashing</code> <code>sha1</code> and <code>md5</code> methods. </p>

<h2>Noncompliant Code Example</h2>
<pre>
MessageDigest md = MessageDigest.getInstance("SHA1");  // Noncompliant
</pre>

<h2>Compliant Solution</h2>
<pre>
MessageDigest md = MessageDigest.getInstance("SHA-256");
</pre>
or
<pre>
Cipher cipher = Cipher.getInstance("AES/CBC/PKCS5PADDING");
</pre>

<h2>See</h2>
<ul>
	<li><a href="http://cwe.mitre.org/data/definitions/328">MITRE, CWE-328</a> - Reversible One-Way Hash</li>
	<li><a href="http://cwe.mitre.org/data/definitions/327">MITRE, CWE-327</a> - Use of a Broken or Risky Cryptographic Algorithm</li>
	<li><a href="https://www.owasp.org/index.php/Top_10_2013-A6-Sensitive_Data_Exposure">OWASP Top Ten 2013 Category A6 - Sensitive Data Exposure</a></li>
	<li><a href="http://www.sans.org/top25-software-errors/">CWE/SANS TOP 25 Most Dangerous Software Errors</a></li>
</ul>

--------



## 831.


*  "Iterator.hasNext()" should not call "Iterator.next()"

system_tags : bug, priority : 4; plugin_rule_key : S1849

Calling <code>Iterator.hasNext()</code> is not supposed to have any side effects, and therefore should not change the state of the iterator. <code>Iterator.next()</code> advances the iterator by one item. So calling it inside <code>Iterator.hasNext()</code>, breaks the <code>hasNext()</code> contract, and will lead to unexpected behavior in production.

<h2>Noncompliant Code Example</h2>
<pre>
public class FibonacciIterator implements Iterator&lt;Integer&gt;{
...
@Override
public boolean hasNext() {
  if(next() != null) {
    return true;
  }
  return false;
}
...
}
</pre>

--------



## 832.


*  Right curly braces should be located at the beginning of lines of code

system_tags : convention, priority : 2; plugin_rule_key : RightCurlyBraceStartLineCheck

<h5>
Sharing some coding conventions is a key point to make it possible for a team to efficiently collaborate.
This rule make it mandatory to place right curly braces at the beginning of lines of code.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
public void myMethod() {
  if(something) {
    executeTask();}                   // Non-Compliant
  else if (somethingElse) {
    doSomethingElse();
  }                                   // Compliant

  try {
    generateOrder();
  } finally {                         // Compliant
    closeConnection();
  }                                   // Compliant

  try {
    generateOrder();
  } finally {                         // Compliant
    closeConnection(); }              // Non-Compliant
}
</pre>

--------



## 833.


*  "public static" fields should always be constant

system_tags : null, priority : 2; plugin_rule_key : S1444

<h5>There is no good reason to declare a field "public" and "static" without also declaring it "final". Most of the time this is a kludge to share a state among several objects. But with this approach, any object can do whatever it wants with the shared state, such as setting it to <code>null</code>.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public class Greeter {
public static var foo:Foo = new Foo(...);
...
}
</pre>

<h2>Compliant Solution</h2>
<pre>
public class Greeter {
public static const FOO:Foo = new Foo(...);
...
}
</pre>

--------



## 834.


*  Classes from "com.sun.*" and "sun.*" packages should not be used

system_tags : null, priority : 2; plugin_rule_key : S1191

<h5>
Classes in <code>com.sun.*</code> and <code>sun.*</code> packages are considered implementation details, and are not part of the Java API.
They can cause problems when moving to new versions of Java because there is no backwards compatibility guarantee.
Such classes are almost always wrapped by Java API classes that should be used instead.
</h5>

<h2>Noncompliant Code Example</h2>

<pre>
import com.sun.jna.Native;     // Non-Compliant
import sun.misc.BASE64Encoder; // Non-Compliant
</pre>

--------



## 835.


*  "enum" should no longer be used as a name

system_tags : null, priority : 2; plugin_rule_key : S1190

<h5>
As of Java 5, <code>enum</code> is a keyword and can therefore no longer be used a variable names for instance.
Recent versions of the Java compiler will generate errors while compiling code still using <code>enum</code> as a name.
</h5>

<p>The following code snippet illustrates this rule:</p>

<pre>
public void doSomething() {
  int enum = 42;            // Non-Compliant
}
</pre>

--------



## 836.


*  Values passed to OS commands should be sanitized

system_tags : cwe,owasp-top10,sans-top25,security, priority : 3; plugin_rule_key : S2076

<h5>Applications that execute operating system commands should neutralize any externally-provided values used in those commands. Failure to do so could allow an attacker to include input that executes unintended commands, or exposes sensitive data.</h5>

<p>This rule logs an issue as soon as a command is built dynamically. it's then up to the auditor to figure out if the command execution is secure or not.</p>

<h2>Noncompliant Code Example</h2>
<pre>
public void listContent(String input) {
  Runtime rt = Runtime.getRuntime();
  rt.exec("ls " + input); // Noncompliant; input could easily contain extra commands
  ...
}

public void execute(String command, String argument) {
  ProcessBuilder pb = new ProcessBuilder(command, argument); // Noncompliant
  ...
}
</pre>

<h2>See</h2>
    <ul>
      <li><a href="http://cwe.mitre.org/data/definitions/78">MITRE, CWE-78</a> - Improper Neutralization of Special Elements used in an OS Command</li>
      <li><a href="http://cwe.mitre.org/data/definitions/88">MITRE, CWE-88</a> - Argument Injection or Modification</li>
      <li><a href="https://www.owasp.org/index.php/Top_10_2013-A1-Injection">OWASP Top Ten 2013 Category A1 - Injection</a></li>
    </ul>

--------



## 837.


*  Exception types should not be tested using "instanceof" in catch blocks

system_tags : error-handling, priority : 2; plugin_rule_key : S1193

<h5>
Multiple catch blocks of the appropriate type should be used instead of catching a general exception, and then testing on the type.
</h5>

<p>For example, following code:</p>

<pre>
try {
  /* ... */
} catch (Exception e) {
  if(e instanceof IOException) { /* ... */ }         // Non-Compliant
  if(e instanceof NullPointerException{ /* ... */ }  // Non-Compliant
}
</pre>

<p>should be refactored into:</p>

<pre>
try {
  /* ... */
} catch (IOException e) { /* ... */ }                // Compliant
} catch (NullPointerException e) { /* ... */ }       // Compliant
</pre>

--------



## 838.


*  String literals should not be duplicated

system_tags : null, priority : 1; plugin_rule_key : S1192

<h5>
  Duplicated string literals make the process of refactoring error-prone, since you must be sure to update all occurrences.
  On the other hand, constants can be referenced from many places, but only need to be updated in a single place.
</h5>

<h2>Non Compliant Code Example</h2>

<pre>
public void run() {
  prepare("action1");                              // Non-Compliant - "action1" is duplicated 3 times
  execute("action1");
  release("action1");
}

@SuppressWarning("all")                            // Compliant - annotations are excluded
private void method1() { /* ... */ }
@SuppressWarning("all")
private void method2() { /* ... */ }

public String method3(String a) {
  System.out.println("'" + a + "'");               // Compliant - literal "'" has less than 5 characters and is excluded
  return "";                                       // Compliant - literal "" has less than 5 characters and is excluded
}
</pre>

<h2>Compliant Code Example</h2>

<pre>
private static final String ACTION_1 = "action1";  // Compliant

public void run() {
  prepare(ACTION_1);                               // Compliant
  execute(ACTION_1);
  release(ACTION_1);
}
</pre>

<h2>Exceptions</h2>
<p>To prevent generating some false-positives, literals having less than 5 characters are excluded.</p>

--------



## 839.


*  Magic numbers should not be used

system_tags : null, priority : 1; plugin_rule_key : S109

<h5>A magic number is a number that comes out of nowhere, and is directly used in a statement. Magic numbers are often used, for instance to limit the number of iterations of a loops, to test the value of a property, etc.</h5>

<p>Using magic numbers may seem obvious and straightforward when you're writing a piece of code, but they are much less obvious and straightforward at debugging time.</p>

<p>That is why magic numbers must be demystified by first being assigned to clearly named constants before being used.</p>

<p>-1, 0 and 1 are not considered magic numbers.</p>

<h2>Noncompliant Code Sample</h2>

<pre>
public static void doSomething() {
  for(int i = 0; i < 4; i++){                 //Non-Compliant, 4 is a magic number
  ...
  }
}
</pre>

<h2>Compliant Solution</h2>

<pre>
public static final int NUMBER_OF_CYCLES = 4;
public static void doSomething() {
  for(int i = 0; i < NUMBER_OF_CYCLES ; i++){   //Compliant
    ...
  }
}
</pre>

--------



## 840.


*  Values passed to SQL commands should be sanitized

system_tags : cwe,owasp-top10,security,sql, priority : 3; plugin_rule_key : S2077

<h5>Applications that execute SQL commands should neutralize any externally-provided values used in those commands. Failure to do so could allow an attacker to include input that changes the query so that unintended commands are executed, or sensitive data is exposed.</h5>

<p>This rule checks that method parameters are not used directly in SQL statements.</p>

<h2>Noncompliant Code Example</h2>
<pre>
public User getUser(Connection con, String user) throws SQLException {

  Statement stmt1 = null;
  Statement stmt2 = null;
  PreparedStatement pstmt;
  try {
    stmt1 = con.createStatement();
    ResultSet rs1 = stmt1.executeQuery("GETDATE()"); // Compliant; parameters not used here

    stmt2 = con.createStatement();
    ResultSet rs2 = stmt2.executeQuery("select FNAME, LNAME, SSN " +
    "from USERS where UNAME=" + user;);  // Noncompliant; parameter concatenated directly into query

    pstmt = con.prepareStatement("select FNAME, LNAME, SSN " +
    "from USERS where UNAME=" + user);  // Noncompliant; parameter concatenated directly into query
    ResultSet rs3 = pstmt.executeQuery();

    //...
public User getUserHibernate(org.hibernate.Session session, String userInput) {

  org.hibernate.Query query = session.createQuery( // Compliant
            "FROM students where fname = " + userInput);  // Noncompliant; parameter binding should be used instead
  // ...
</pre>

<h2>Compliant Solution</h2>
<pre>
public User getUser(Connection con, String user) throws SQLException {

  Statement stmt1 = null;
  PreparedStatement pstmt = null;
  String query = "select FNAME, LNAME, SSN from USERS where UNAME=?";
  try {
    stmt1 = con.createStatement();
    ResultSet rs1 = stmt1.executeQuery("GETDATE()");

    pstmt = con.prepareStatement(query);
    pstmt.setString(1, user);  // Compliant; PreparedStatements escape their inputs.
    ResultSet rs2 = pstmt.executeQuery();
    //...

public User getUserHibernate(org.hibernate.Session session, String userInput) {

  org.hibernate.Query query =  session.createQuery("FROM students where fname = ?"); //Compliant
  query = query.setParameter(0,userInput);  // Parameter binding escapes all input
  // ...
</pre>

<h2>See</h2>
<ul>
  <li><a href="http://cwe.mitre.org/data/definitions/89">MITRE, CWE-89</a> - Improper Neutralization of Special Elements used in an SQL Command</li>
  <li><a href="http://cwe.mitre.org/data/definitions/564.html">MITRE, CWE-564</a> - SQL Injection: Hibernate</li>
  <li><a href="http://cwe.mitre.org/data/definitions/20.html">MITRE, CWE-20</a> - Improper Input Validation</li>
  <li><a href="http://cwe.mitre.org/data/definitions/943.html">MITRE, CWE-943</a> - Improper Neutralization of Special Elements in Data Query Logic</li>
</ul>

--------



## 841.


*  Values passed to LDAP queries should be sanitized

system_tags : cwe,owasp-top10,security, priority : 3; plugin_rule_key : S2078

<h5>Applications that execute LDAP queries should neutralize any externally-provided values in those commands. Failure to do so could allow an attacker to include input that changes the query so that unintended commands are executed, or sensitive data is exposed. Unhappily LDAP doesn't provide any prepared statement interfaces like SQL to easily remove this risk. So each time a LDAP query is built dynamically this rule logs an issue.</h5>

<h2>Noncompliant Code Example</h2>
<pre>
public User lookupUser(String username, String base, String [] requestedAttrs) {

// ...
DirContext dctx = new InitialDirContext(env);

SearchControls sc = new SearchControls();
sc.setReturningAttributes(requestedAttrs);  // Noncompliant
sc.setSearchScope(SearchControls.SUBTREE_SCOPE);

String filter = "(&(objectClass=user)(sAMAccountName=" + username + "))";

NamingEnumeration results = dctx.search(base,  // Noncompliant
filter,  // Noncompliant; parameter concatenated directly into string
sc);
</pre>

<h2>Compliant Solution</h2>
<pre>
public User lookupUser(String username, String base, String [] requestedAttrs) {

// ...
DirContext dctx = new InitialDirContext(env);

SearchControls sc = new SearchControls();
sc.setReturningAttributes(buildAttrFilter(requestedAttrs));  // Compliant; method presumably scrubs input
sc.setSearchScope(SearchControls.SUBTREE_SCOPE);

String useBase = "ou=People";
if (! base.startsWith(useBase)) {
useBase = base;
}

String filter = "(&(objectClass=user)(sAMAccountName=" + username.replaceAll("[()| ]","") + "))";

NamingEnumeration results = dctx.search(useBase,  // Compliant; originally value used conditionally
filter,  // Compliant; parameter NOT concatenated directly into string
sc);
</pre>

<h2>See</h2>
<ul>
  <li><a href="http://cwe.mitre.org/data/definitions/90">MITRE CWE-90</a> - Improper Neutralization of Special Elements used in an LDAP Query ('LDAP Injection')</li>
  <li><a href="https://www.owasp.org/index.php/Top_10_2013-A1-Injection">OWASP Top Ten 2013 Category A1 - Injection</a></li>
</ul>

--------



## 842.


*  Array designators "[]" should be located after the type in method signatures

system_tags : convention, priority : 1; plugin_rule_key : S1195

<h5>
According to the Java Language Specification:
</h5>

<pre>
For compatibility with older versions of the Java SE platform,
the declaration of a method that returns an array is allowed to place (some or all of) the empty bracket pairs that form the declaration of the array type after the formal parameter list.
This obsolescent syntax should not be used in new code.
</pre>

<p>The following code snippet illustrates this rule:</p>

<pre>
public int getVector()[] { /* ... */ }    // Non-Compliant

public int[] getVector() { /* ... */ }    // Compliant

public int[] getMatrix()[] { /* ... */ }  // Non-Compliant

public int[][] getMatrix() { /* ... */ }  // Compliant
</pre>

--------



## 843.


*  System.out and System.err should not be used as loggers

system_tags : null, priority : 2; plugin_rule_key : S106

<h5>Two important requirements must be fulfilled when logging messages:</h5>

<ul>
  <li>The user must be able to easily retrieve the logs.</li>
  <li>The format of all messages must be uniform to enable users to easily browse them.</li>
</ul>

<p>
If a program directly writes to the standard output, there is absolutely no way to comply with these requirements.
That's why defining and using a dedicated logger is highly recommended.
</p>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
System.out.println("My Message");  // Non-Compliant

logger.log("My Message");          // Compliant
</pre>

--------



## 844.


*  "java.lang.Error" should not be extended

system_tags : error-handling, priority : 2; plugin_rule_key : S1194

<h5>
<code>java.lang.Error</code> and its subclasses represent abnormal conditions, such as <code>OutOfMemoryError</code>, which should only be encountered by the Java Virtual Machine.
</h5>

<p>The following code snippet:</p>

<pre>
public class MyException extends Error { /* ... */ }       // Non-Compliant
</pre>

<p>should be refactored into:</p>

<pre>
public class MyException extends Exception { /* ... */ }   // Compliant
</pre>

--------



## 845.


*  super.finalize() should be called at the end of Object.finalize() implementations

system_tags : bug, priority : 4; plugin_rule_key : ObjectFinalizeOverridenCallsSuperFinalizeCheck

<h5>
Overriding the <code>Object.finalize()</code> method must be done with caution to dispose some system resources.
Calling the <code>super.finalize()</code> at the end of this method implementation is highly recommended in case parent implementations must also dispose some system resources.
</h5>

<p>
The following code snippet illustrates this rule:
</p>

<pre>
protected void finalize() {            // Non-Compliant
  releaseSomeResources();
}

protected void finalize() {
  super.finalize();                    // Non-Compliant
  releaseSomeResources();
}

protected void finalize() {
  releaseSomeResources();
  super.finalize();                    // Compliant
}
</pre>

--------










