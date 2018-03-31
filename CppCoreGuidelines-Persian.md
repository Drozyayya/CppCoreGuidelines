<p align="center">
بسم الله الرحمن الرحیم

<div dir="rtl">
  
# <a name="main"></a>رهنمود‌های بنیادین سی پلاس پلاس

۱۳ رجب ۱۴۳۹

بروز رسانی از مرجع: March 26, 2018

ویراستاران:

* سید سروش حسین‌علی‌پور

این سند هنوز در مراحل اولیه خود می‌باشد و شامل نواقص، ابهامات و یا حتی اشکلاتی می‌باشد.
این مستند یک پروژه متن باز می‌باشد و تا کنون نسخه فارسی آن انتشاری نداشته است، اما از [سند مرجع](./CppCoreGuidelines.md) نسخه [۰٫۸](https://github.com/isocpp/CppCoreGuidelines/releases) متنشر شده است.

رونوشت‌برداری، استفاده، تغییر و هرگونه اشقاق‌گیری پایین دستی از این پروژه تحت مجوز MIT-style می‌باشد.
مشارکت در این پروژه به معنای پذیرش شرایط مشارکت می‌باشد. برای اطلاعات بیشتر به پرونده [مجوز](LICENSE) مراجعه فرمایید.
ما این پروژه را به این امید در دسترس همکاران و متخصصان این حوزه برای استفاده، رونوشت‌برداری، تغییر و انشقاق‌گیری قرار دادیم که با نظرات ارزشمند خود ما را یاری کنند.

پیشاپیش از هرگونه نظر و پیشنهاد که منجر به بهبود این سند گردد استقبال می‌نماییم.
ما ان‌شا‌الله برنامه داریم که با افزایش آگاهی خود از پروژه‌های بزرگ در این حوزه و همینطور مفاهیم و مقتضیات زبان این سند را توسعه دهیم و همچنین موارد بیشتری را از سند مرجع در این سند بیاوریم.
زمانی که می‌خواهید مشارکت کنید و یا نظری بدهید، لطفا بخش [مقدمه](#S-introduction) را مطالعه بفرمایید که چهارچوب‌ها و اهداف ما در آن مشخص شده است و ناظر به این اهداف و چهارچوب‌ها نظرات گران‌بهای خود را در اختیار ما بگذارید.
لیست مشارکت کنندگان در [اینجا](#SS-ack) قابل دسترس است.

مشکلات:

* بعضی از قوانین هنوز جامع و مانع، سازگار و یا به اندازه کافی الزام آور نمی‌باشند
* مکان‌هایی از سند که (???) علامت گذاری شده‌اند دارای نقص اطلاعات می‌باشند
* وجود لیست کار‌هایی که باید در آینده انجام شود در بخش [کار‌های آینده - To-do: Unclassified proto-rules](#S-unclassified)

شما می‌توانید [توضیحات مربوط به حوزه سند و ساختار سند](#S-abstract) را مطالعه بفرمایید و یا اینکه مستقیما هرکدام از بخش‌های زیر را بخوانید

* [In: Introduction](#S-introduction)
* [P: Philosophy](#S-philosophy)
* [I: Interfaces](#S-interfaces)
* [F: Functions](#S-functions)
* [C: Classes and class hierarchies](#S-class)
* [Enum: Enumerations](#S-enum)
* [R: Resource management](#S-resource)
* [ES: Expressions and statements](#S-expr)
* [Per: Performance](#S-performance)
* [CP: Concurrency and parallelism](#S-concurrency)
* [E: Error handling](#S-errors)
* [Con: Constants and immutability](#S-const)
* [T: Templates and generic programming](#S-templates)
* [CPL: C-style programming](#S-cpl)
* [SF: Source files](#S-source)
* [SL: The Standard Library](#S-stdlib)

بخش‌های الحاقیه و تکمیلی:

* [A: Architectural ideas](#S-A)
* [NR: Non-Rules and myths](#S-not)
* [RF: References](#S-references)
* [Pro: Profiles](#S-profile)
* [GSL: Guideline support library](#S-gsl)
* [NL: Naming and layout rules](#S-naming)
* [FAQ: Answers to frequently asked questions](#S-faq)
* [Appendix A: Libraries](#S-libraries)
* [Appendix B: Modernizing code](#S-modernizing)
* [Appendix C: Discussion](#S-discussion)
* [Appendix D: Supporting tools](#S-tools)
* [Glossary](#S-glossary)
* [To-do: Unclassified proto-rules](#S-unclassified)

بعضی از قوانین نمونه برای بعضی از قابلیت‌ها و مفاهیم زبان:

* assignment:
[regular types](#Rc-regular) --
[prefer initialization](#Rc-initialize) --
[copy](#Rc-copy-semantics) --
[move](#Rc-move-semantics) --
[other operations](#Rc-matched) --
[default](#Rc-eqdefault)
* `class`:
[data](#Rc-org) --
[invariant](#Rc-struct) --
[members](#Rc-member) --
[helpers](#Rc-helper) --
[concrete types](#SS-concrete) --
[ctors, =, and dtors](#S-ctor) --
[hierarchy](#SS-hier) --
[operators](#SS-overload)
* `concept`:
[rules](#SS-concepts) --
[in generic programming](#Rt-raise) --
[template arguments](#Rt-concepts) --
[semantics](#Rt-low)
* constructor:
[invariant](#Rc-struct) --
[establish invariant](#Rc-ctor) --
[`throw`](#Rc-throw) --
[default](#Rc-default0) --
[not needed](#Rc-default) --
[`explicit`](#Rc-explicit) --
[delegating](#Rc-delegating) --
[`virtual`](#Rc-ctor-virtual)
* derived `class`:
[when to use](#Rh-domain) --
[as interface](#Rh-abstract) --
[destructors](#Rh-dtor) --
[copy](#Rh-copy) --
[getters and setters](#Rh-get) --
[multiple inheritance](#Rh-mi-interface) --
[overloading](#Rh-using) --
[slicing](#Rc-copy-virtual) --
[`dynamic_cast`](#Rh-dynamic_cast)
* destructor:
[and constructors](#Rc-matched) --
[when needed?](#Rc-dtor) --
[may not fail](#Rc-dtor-fail)
* exception:
[errors](#S-errors) --
[`throw`](#Re-throw) --
[for errors only](#Re-errors) --
[`noexcept`](#Re-noexcept) --
[minimize `try`](#Re-catch) --
[what if no exceptions?](#Re-no-throw-codes)
* `for`:
[range-for and for](#Res-for-range) --
[for and while](#Res-for-while) --
[for-initializer](#Res-for-init) --
[empty body](#Res-empty) --
[loop variable](#Res-loop-counter) --
[loop variable type ???](#Res-???)
* function:
[naming](#Rf-package) --
[single operation](#Rf-logical) --
[no throw](#Rf-noexcept) --
[arguments](#Rf-smart) --
[argument passing](#Rf-conventional) --
[multiple return values](#Rf-out-multi) --
[pointers](#Rf-return-ptr) --
[lambdas](#Rf-capture-vs-overload)
* `inline`:
[small functions](#Rf-inline) --
[in headers](#Rs-inline)
* initialization:
[always](#Res-always) --
[prefer `{}`](#Res-list) --
[lambdas](#Res-lambda-init) --
[in-class initializers](#Rc-in-class-initializer) --
[class members](#Rc-initialize) --
[factory functions](#Rc-factory)
* lambda expression:
[when to use](#SS-lambdas)
* operator:
[conventional](#Ro-conventional) --
[avoid conversion operators](#Ro-conventional) --
[and lambdas](#Ro-lambda)
* `public`, `private`, and `protected`:
[information hiding](#Rc-private) --
[consistency](#Rh-public) --
[`protected`](#Rh-protected)
* `static_assert`:
[compile-time checking](#Rp-compile-time) --
[and concepts](#Rt-check-class)
* `struct`:
[for organizing data](#Rc-org) --
[use if no invariant](#Rc-struct) --
[no private members](#Rc-class)
* `template`:
[abstraction](#Rt-raise) --
[containers](#Rt-cont) --
[concepts](#Rt-concepts)
* `unsigned`:
[and signed](#Res-mix) --
[bit manipulation](#Res-unsigned)
* `virtual`:
[interfaces](#Ri-abstract) --
[not `virtual`](#Rc-concrete) --
[destructor](#Rc-dtor-virtual) --
[never fail](#Rc-dtor-fail)

مفاهیم طراحی و ملاحظاتی که بر اساس آن‌ها قوانین نگاشته شده‌اند:

* assertion: ???
* error: ???
* exception: exception guarantee (???)
* failure: ???
* invariant: ???
* leak: ???
* library: ???
* precondition: ???
* postcondition: ???
* resource: ???

# <a name="S-abstract"></a>خلاصه
