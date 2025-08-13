# 🌸 UNIT 3 - QUIZZ

## 💮 You implement the behavior of a business object in the ABAP RESTful application programming model. Which of the following method calls create messages which are translatable?

_There are two correct answers._

- [ ] DATA(msg) = me->new_message_with_text( severity = ms-error text = |Airport does not exist| ).

- [ ] DATA(msg) = me->new_message_with_text( severity = ms-error text = |{ 'Airport does not exist'(ane) } | ).

- [ ] DATA(msg) = me->new_message_with_text( severity = ms-error text = 'Airport does not exist'(ane) ).

- [ ] DATA(msg) = me->new_message_with_text( severity = ms-error text = 'Airport does not exist ' ).

<details>
  <summary>Solution</summary>

- [ ] DATA(msg) = me->new_message_with_text( severity = ms-error text = |Airport does not exist| ).

- [x] DATA(msg) = me->new_message_with_text( severity = ms-error text = |{ 'Airport does not exist'(ane) } | ).

- [x] DATA(msg) = me->new_message_with_text( severity = ms-error text = 'Airport does not exist'(ane) ).

- [ ] DATA(msg) = me->new_message_with_text( severity = ms-error text = 'Airport does not exist ' ).

</details>

## 💮 An ABAP built-in function xyz( ) is called in the following way: IF xyz( …. ) . … ENDIF. What does this tell you about the nature of the function?

_Choose the correct answer._

- [ ] xyz( ) is a description function.

- [ ] xyz( ) is a predicate function.

- [ ] xyz( ) is a processing function.

<details>
  <summary>Solution</summary>

- [ ] xyz( ) is a description function.

- [x] xyz( ) is a predicate function.

- [ ] xyz( ) is a processing function.

</details>

## 💮 True or False? When you call a built-in string function without supplying optional parameter CASE, processing is case-sensitive.

_Choose the correct answer._

- [ ] True

- [ ] False

<details>
  <summary>Solution</summary>

- [x] True

- [ ] False

</details>

## 💮 Which of the following are subject to translation in ABAP?

_There are three correct answers._

- [ ] The value of annotation @enduserText.Label in a data definition

- [ ] The value of a text literal in the source code of an ABAP class

- [ ] The short text of a message text in a message class

- [ ] The value of a text symbol in an ABAP class

<details>
  <summary>Solution</summary>

- [x] The value of annotation @enduserText.Label in a data definition

- [ ] The value of a text literal in the source code of an ABAP class

- [x] The short text of a message text in a message class

- [x] The value of a text symbol in an ABAP class

</details>

## 💮 There is a simple translation tool that is integrated into ADT.

_Choose the correct answer._

- [ ] True

- [ ] False

<details>
  <summary>Solution</summary>

- [ ] True

- [x] False

</details>

## 💮 True or False? ABAP only supports Perl Compatible Regular Expression (PCRE).

_Choose the correct answer._

- [ ] True

- [ ] False

<details>
  <summary>Solution</summary>

- [ ] True

- [x] False

</details>
