Download Link: https://assignmentchef.com/product/solved-nwen241-assignment-1-text-editor
<br>
<strong>“Skeleton” Files</strong>

In this assignment, you will be given the following skeleton files which should be under the files directory in the archive that contains this file.

<ol>

 <li>h – C header file that contains macro definitions and all the required function prototypes for Part I. <em>Do not modify this file!</em></li>

 <li>hh – C++ header file that contains macro and class definitions for Part II. <em>Do not modify this file!</em></li>

 <li>hh – Empty C++ header file that you will use to define your class for Part II.</li>

 <li>c – Empty C file that you will use to implement functions for Part I. You are free to implement other functions within this file that you think are needed to fulfil the tasks.</li>

 <li>cc – Empty C++ file that implements your class for Part</li>

</ol>

II.

To get a better understanding of the tasks, you should read this document together with the provided skeleton code.

<strong>Coding Style</strong>

Coding style (also known as coding standard) refers to the use of appropriate indentation, proper placement of braces, proper formatting of control constructs, etc. Following a particular coding style consistently will make your source code more readable.

There are many coding standards available (search “C/C++ coding style”). Most of these standards are dense and will take you many days (even weeks) to read and understand. If you want to follow a <em>lightweight </em>coding style, consult the Linux kernel coding style (<a href="https://www.kernel.org/doc/html/v4.10/process/coding-style.html">https://www.kernel. </a><a href="https://www.kernel.org/doc/html/v4.10/process/coding-style.html">org/doc/html/v4.10/process/coding-style.html</a><a href="https://www.kernel.org/doc/html/v4.10/process/coding-style.html">)</a>. You only need to read sections 1–3 of this document.

Note that you do not have to follow every recommendation you can find in a coding style document. If you change, for instance the tab size from 8 to 4, that is fine. You just have to apply that style consistently.

<strong>Editing Buffer</strong>

An important component of a text editor is the <em>editing buffer </em>which is essentially a block of computer memory that contains part of the text document being edited. It can be viewed as one-dimensional array of characters from the perspective of the programmer.

<strong>Part I: Pure C Programming</strong>

You may only use the Standard C Library to perform the tasks in this part. You should implement the functions in editor.c.

<strong>Task 1.</strong>

Basics [10 Marks]

In this task, you will implement a function with prototype

<strong>int </strong>editor_insert_char(<strong>char </strong>*editing_buffer, <strong>char </strong>to_insert, <strong>int </strong>pos)

which will insert the character to_insert at index pos of editing_buffer. The size of editing_buffer is EDITING_BUFLEN. When a character is inserted at index pos, each of the original characters at index pos until the end of buffer must be moved by one position to the right. The last character is thrown out.

The function should return 1 if the character insertion occurred, otherwise it should return 0.

To clarify, suppose that EDITING_BUFLEN is defined to be 21 and the contents of editing_buffer are

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

After invoking

<strong>int </strong>r = editor_insert_char(editing_buffer, ’s’, 9);

the contents of editing_buffer should be

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

and the value of r is 1.

<strong>Task 2.</strong>

Basics [10 Marks]

In this task, you will implement a function with prototype

<strong>int </strong>editor_delete_char(<strong>char </strong>*editing_buffer, <strong>char </strong>to_delete, <strong>int </strong>offset)

which will delete the first occurrence of the character to_delete. The search should start from index offset of editing_buffer. The size of editing_buffer is EDITING_BUFLEN. When a character is deleted at index pos, each of the original characters at index pos until the end of buffer must be moved by one position to the left. A null character is inserted at the end of the buffer.

The function should return 1 if the character deletion occurred, otherwise it should return 0.

To clarify, suppose that EDITING_BUFLEN is defined to be 21 and the contents of editing_buffer are

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

After invoking

<strong>int </strong>r = editor_delete_char(editing_buffer, ’f’, 10);

the contents of editing_buffer should be

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

and the value of r is 1.

<strong>Task 3.</strong>

Completion [10 Marks]

In this task, you will implement a function with prototype

<strong>int </strong>editor_replace_str(<strong>char </strong>*editing_buffer, <strong>const char </strong>*str, <strong>const char </strong>*replacement, <strong>int </strong>offset)

which will replace the first occurrence of the string str with replacement. The search should start from index offset of editing_buffer. The size of editing_buffer is EDITING_BUFLEN.

The replacement should not overwrite other contents in the buffer. This means that if replacement is longer than str, there is a need move the characters after str to the right. Likewise, if replacement is shorter than str, there is a need move the characters after str to the left. When moving characters to the right, throw out characters that will not fit in the buffer. When moving characters to the left, insert null characters in the vacated positions.

If the replacement text will go beyond the limits of editing_buffer, then replacement should only occur until the end of editing_buffer.

If the string replacement occurred, the function should return the index corresponding the last letter of replacement in editing_buffer, otherwise, it should return -1. If the replacement text will go beyond the limits of editing_buffer, the function should return EDITING_BUFLEN-1.

To clarify, suppose that EDITING_BUFLEN is defined to be 21 and the contents of editing_buffer are

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

After invoking

<strong>int </strong>r = editor_replace_str(editing_buffer, “brown”, “blue”, 0);

the contents of editing_buffer should be

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

and the value of r should be 13 (which is the index of ’e’ in “blue”).

<strong>Task 4.</strong>

Challenge [10 Marks]

In this task, you will implement a function with prototype

<strong>void </strong>editor_view(<strong>char </strong>**viewing_buffer, <strong>const char </strong>*editing_buffer, <strong>int </strong>wrap)

which will essentially copy the contents of the editing_buffer to the viewing_buffer for display to the user. Note that the latter is a twodimensional array, with dimensions VIEWING_COLS columns and VIEWING_ROWS rows. VIEWING_COLS and VIEWING_ROWS are defined in editor.h. Prior to the copying, the function must set every character in the viewing_buffer to the null character.

The argument wrap controls the behaviour of the copying process from editing_buffer to viewing_buffer as follows:

<ul>

 <li>Regardless of the value of<sub>encountered, subsequent text after the newline charater is copied to</sub>wrap, whenever a newline character is the next row. Note that the newline character itself is not copied to viewing_buffer.</li>

 <li>When<sub>when the newline character is</sub>wrap is non-zero, the text must be wrapped. This means that<em><sub>not </sub></em>encountered before the end of the</li>

</ul>

current row (at column VIEWING_COLS-1 in viewing_buffer), subsequent text is copied to the next row. Note that column VIEWING_COLS-1 in viewing_buffer is never filled and will retain the null character.

<ul>

 <li>When<sub>newline character is</sub>wrap is 0, the text is not wrapped. This means that when the<em><sub>not </sub></em>encountered before the end of the current row</li>

</ul>

(at column VIEWING_COLS-1), succeeding text in the editing_buffer are discarded until a newline is encountered which will cause the succeeding text to be copied to the next row. Note that column VIEWING_COLS-1 in viewing_buffer is never filled and will retain the null character.

The copying process should terminate when a null character is encountered.

To clarify, suppose that EDITING_BUFLEN is defined to be 48 and the contents of editing_buffer are

<table width="387">

 <tbody>

  <tr>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"> </td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"> </td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

  </tr>

 </tbody>

</table>

Suppose that VIEWING_COLS and VIEWING_ROWS are 11 and 8, respectively. After invoking

editor_view(viewing_buffer, editing_buffer, 1);

the resulting contents of viewing_buffer should be

editor_view(viewing_buffer, editing_buffer, 0);

the resulting contents of viewing_buffer should be

<strong>Part II: C++ Programming</strong>

You may use the C++ Standard Library to perform the tasks in this part.

<strong>Task 5.</strong>

Basics [10 Marks]

In this task, you will define a class that extends the EditingBuffer class defined in editor.hh. You should declare the class in myeditor.hh and name it MyEditingBuffer. This class should be in same namespace as EditingBuffer. The access mode of the inherited members should be preserved.

You are free to declare additional member variables and functions that are necessary to perform the subsequent tasks. Provide sufficient comment, and ensure that these additional member variables and functions are <em>not </em>publicly accessible.

<strong>Task 6.</strong>

Basics [10 Marks]

In this task, you will implement the member function

<strong>bool </strong>replace(<strong>char </strong>c, <strong>char </strong>replacement, <strong>int </strong>offset)

which will replace the first occurrence of the character c with replacement in the buffer. The search should start from index offset of buffer. The length of buffer is BUFFER_LEN which is defined in editor.hh.

The function should return true if the character insertion occurred, otherwise false.

To clarify, suppose that BUFFER_LEN is defined to be 21 and the contents of buffer are

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

After invoking

MyEditingBuffer meb; …

<strong>bool </strong>r = meb.replace(’b’, ’B’, 5);

the resulting contents of the buffer should be

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

and the value of r should true.

You should implement this member function in myeditor.cc.

<strong>Task 7.</strong>

Completion [10 Marks]

In this task, you will implement the member function

<strong>int </strong>replace(std::string str, std::string replacement, <strong>int </strong>offset)

which will replace the first occurrence of the string str with replacement. The search should start from index offset of buffer.

The replacement should not overwrite other contents in the buffer. This means that if replacement is longer than str, there is a need move the characters after str to the right. Likewise, if replacement is shorter than str, there is a need move the characters after str to the left. When moving characters to the right, throw out characters that will not fit in the buffer. When moving characters to the left, insert null characters in the vacated positions.

If the replacement text will go beyond the limits of buffer, then replacement should only occur until the end of buffer.

If the string replacement occurred, the function should return the index corresponding the last letter of str in editing_buffer, otherwise, it should return -1. If the replacement text will go beyond the limits of buffer, the function should return BUFFER_LEN-1.

To clarify, suppose that BUFFER_LEN is defined to be 21 and the contents of buffer are

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

After invoking

MyEditingBuffer meb; … std::string s(“brown”); std::string t(“violet”); <strong>int </strong>r = meb.replace(s, t, 8);

the resulting contents of the buffer should be

<table width="476">

 <tbody>

  <tr>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"> </td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

   <td width="23"></td>

  </tr>

 </tbody>

</table>

and the value of r should be 15 (which is the index of ’t’ in “violet”). You should implement this member function in myeditor.cc.

<strong>Task 8.</strong>

Challenge [15 Marks]

In this task, you will implement the member function

<strong>void </strong>justify(<strong>char </strong>**viewingBuffer, <strong>int </strong>rows, <strong>int </strong>cols)

which will justify the contents of buffer by adjusting the space in between words. The justified text should be stored in viewingBuffer, a two-dimensional array which has rows rows and cols columns.

To implement the text justification, the contents of buffer must first be copied to viewingBuffer such that the copied text is wrapped. You may reuse your implementation in Task 4 for this purpose.

After copying, the contents of viewingBuffer must be justified, i.e., <strong>the character at column </strong>cols-2 <strong>of every row must not be a whitespace if possible</strong>. This can be done by adding whitespaces in between words. When justifying, follow these guidelines:

<ol>

 <li>Do not justify empty rows (rows consisting of null characters) and single-word rows.</li>

 <li>Do not split words, <em>e.</em>, do not insert spaces in between the letters of a word.</li>

 <li>You can split a single-word row if the single word is too long to fit one row.</li>

 <li>Do not merge words.</li>

 <li></li>

</ol>

<table>

 <tbody>

  <tr>

   <td width="167"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

<ul>

 <li>If necessary, discard characters that will not fit in the buffer.</li>

</ul>

To clarify, suppose that BUFFER_LEN is defined to be 48 and the contents of buffer are

<table width="387">

 <tbody>

  <tr>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"> </td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"> </td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

   <td width="24"></td>

  </tr>

 </tbody>

</table>

After invoking

MyEditingBuffer meb; … meb.justify(viewingBuffer, 8, 11);

the resulting contents of viewingBuffer should be

You should implement this member function in myeditor.cc.

<strong>Part III: Systems Program Design</strong>

In Parts I and II, you implemented some functionality for manipulating the contents of the editing buffer. In this part, you will <em>design </em>a C++ program for manipulating the <em>viewing buffer</em>.

<strong>Task 9.</strong>

Challenge [15 Marks]

The <em>viewing buffer </em>is a block of computer memory that contains part of the text document shown in the computer display. It can be viewed as a twodimensional array of characters, where the each row corresponds to a line of text. In practice, the number of rows and columns should be determined by the size of the display/terminal. For simplicity, fix the number of rows and columns to 25 and 80, respectively.

In designing the program, assume that a <em>main buffer </em>contains the entire text document being edited. Assume that the main buffer variable is global and is declared as char main_buffer[1000000] somewhere.

The following functionality are required to manipulate the viewing buffer:

<ul>

 <li>Load parts of text document from main buffer to the viewing buffer(from a given line/row position).</li>

 <li>Scroll up viewing buffer content by a given number of lines/rows.</li>

 <li>Scroll down viewing buffer content by a given number of lines/rows.</li>

 <li>Enable wrapping</li>

 <li>Disable wrapping</li>

 <li>Show line numbering</li>

 <li>Hide line numbering</li>

</ul>