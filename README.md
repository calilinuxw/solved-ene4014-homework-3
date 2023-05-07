Download Link: https://assignmentchef.com/product/solved-ene4014-homework-3
<br>
<strong>Exercise 1 </strong>Consider the following programming language, called miniML, that features (recursive) procedures and explicit references.

<strong>Syntax       </strong>The syntax is defined as follows:

<table width="219">

 <tbody>

  <tr>

   <td width="24"><em>P</em></td>

   <td width="27">→</td>

   <td width="169"><em>E</em></td>

  </tr>

  <tr>

   <td width="24"><em>E</em></td>

   <td width="27">→</td>

   <td width="169"><em>n</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169"><em>x</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169"><em>E </em>+ <em>E </em>| <em>E </em>− <em>E </em>| <em>E </em>∗ <em>E </em>| <em>E/E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169"><em>E </em>− <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">iszero <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">if <em>E </em>then <em>E </em>else <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">let <em>x </em>= <em>E </em>in <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">letrec <em>f</em>(<em>x</em>) = <em>E </em>in <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">proc <em>x E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169"><em>E E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">ref <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">! <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169"><em>E </em>:= <em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169"><em>E</em>;<em>E</em></td>

  </tr>

  <tr>

   <td width="24"> </td>

   <td width="27">|</td>

   <td width="169">begin <em>E </em>end</td>

  </tr>

 </tbody>

</table>

<strong>Semantics      </strong>The semantics is defined with the following domain:

<table width="369">

 <tbody>

  <tr>

   <td width="91"><em>Val</em></td>

   <td width="24">=</td>

   <td width="255">Z + <em>Bool </em>+ <em>Procedure </em>+ <em>RecProcedure </em>+ <em>Loc</em></td>

  </tr>

  <tr>

   <td width="91"><em>Procedure</em></td>

   <td width="24">=</td>

   <td width="255"><em>Var </em>× <em>E </em>× <em>Env</em></td>

  </tr>

  <tr>

   <td width="91"><em>RecProcedure</em></td>

   <td width="24">=</td>

   <td width="255"><em>Var </em>× <em>Var </em>× <em>E </em>× <em>Env</em></td>

  </tr>

  <tr>

   <td width="91"><em>ρ </em>∈ <em>Env</em></td>

   <td width="24">=</td>

   <td width="255"><em>Var </em>→ <em>Val</em></td>

  </tr>

  <tr>

   <td width="91"><em>σ </em>∈ <em>Mem</em></td>

   <td width="24">=</td>

   <td width="255"><em>Loc </em>→ <em>Val</em></td>

  </tr>

 </tbody>

</table>

1

and evaluation rules:

<em>ρ,σ</em><sub>0        </sub>0<em>,σ</em><sub>1                 </sub><em>ρ,σ</em><sub>0</sub>

<em>ρ,σ</em><sub>0 </sub>` iszero <em>E </em>⇒ <em>true,σ</em><sub>1                                  </sub><em>ρ,σ</em><sub>0 </sub>` iszero

<em>ρ,σ</em><sub>0 </sub>` <em>E</em><sub>1 </sub>⇒ <em>true,σ</em><sub>1                                </sub><em>ρ,σ</em><sub>1 </sub>` <em>E</em><sub>2 </sub>⇒ <em>v,σ</em><sub>2</sub>

<em>ρ,σ</em><sub>0 </sub>` if <em>E</em><sub>1 </sub>then <em>E</em><sub>2 </sub>else <em>E</em><sub>3 </sub>⇒ <em>v,σ</em><sub>2</sub>

<em>ρ,σ</em><sub>0 </sub>` <em>E</em><sub>1 </sub>⇒ <em>false,σ</em><sub>1                                </sub><em>ρ,σ</em><sub>1 </sub>` <em>E</em><sub>3 </sub>⇒ <em>v,σ</em><sub>2</sub>

<em>ρ,σ</em><sub>0 </sub>` if <em>E</em><sub>1 </sub>then <em>E</em><sub>2 </sub>else <em>E</em><sub>3 </sub>⇒ <em>v,σ</em><sub>2</sub>

<em>ρ,σ</em><sub>0 </sub>` <em>E</em><sub>1 </sub>⇒ <em>v</em><sub>1</sub><em>,σ</em><sub>1                               </sub>[<em>x </em>7→ <em>v</em><sub>1</sub>]<em>ρ,σ</em><sub>1 </sub>` <em>E</em><sub>2 </sub>⇒ <em>v,σ</em><sub>2</sub>

<em>ρ,σ</em><sub>0 </sub>` let <em>x </em>= <em>E</em><sub>1 </sub>in <em>E</em><sub>2 </sub>⇒ <em>v,σ</em><sub>2</sub>

[<em>f </em>7→ (<em>f,x,E</em><sub>1</sub><em>,ρ</em>)]<em>ρ,σ</em><sub>0 </sub>` <em>E</em><sub>2 </sub>⇒ <em>v,σ</em><sub>1</sub>

<em>ρ,σ </em>` letrec <em>f</em>(<em>x</em>) = <em>E </em>in <em>E </em>⇒ <em>v,σ ρ,σ </em>` proc <em>x E </em>⇒ (<em>x,E,ρ</em>)<em>,σ</em>

Dom(<em>σ</em><sub>1</sub>)

<em>ρ,σ</em><sub>0 </sub>` <em>E </em>⇒ <em>v,σ</em><sub>1</sub>

<em>ρ,σ</em><sub>0 </sub>` begin <em>E </em>end ⇒ <em>v,σ</em><sub>1</sub>

Implement an interpreter of miniML. Raise an exception UndefinedSemantics whenever the semantics is undefined. Skeleton code will be provided (before you start, see README.md).

2