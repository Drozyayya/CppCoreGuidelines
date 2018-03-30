<p align="center">
بسم الله الرحمن الرحیم



[![C++ Core Guidelines](cpp_core_guidelines_logo_text.png)](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)

>"Within C++ is a smaller, simpler, safer language struggling to get out."
>-- <cite>Bjarne Stroustrup</cite>

<div dir="rtl">

[رهنمودهای بنیادین سی پلاس پلاس](CppCoreGuidelines-Persian.md) با تلاش بزرگان این زبان از جمله سازنده اصلی تولید و نگهداری می گردد و در اینجا ما یک نسخه کوچک تر شده و فارسی از آن را ارایه می کینم که برای شرکت های که با این زبان کار می کنند ان شا الله مفید واقع شود

## شروع کنید

دو مستند وجود دارد یکی نسخه مرجع که در [CppCoreGuidelines](CppCoreGuidelines.md) قابل خواندن است و نسخه‌ای است که بر اساس آن مستند فارسی توسعه داده شده است، نسخه دوم نسخه فارسی می‌باشد که در [رهنمود‌های بنیادین سی پلاس پلاس](CppCoreGuidelines-Persian.md)  قابل خواندن است و آخرین نکات تایید شده برای رعایت شدن در شرکت‌ها در آن آمده است

[یک نسخه مناسب برای مرورگر](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines) به زبان انگلیسی نیز وجود دارد که به صورت دستی بروزرسانی می‌گردد و معمولا از آخرین تغییرات عقب تر است

این مستند به ان‌شا‌الله به طور مدام در [مخزن مرجع بروزرسانی](https://github.com/isocpp/CppCoreGuidelines) می‌گردد و به تبع آن ان‌شا‌الله در اینجا نیز تغییرات به صورت دوره‌ای بروزرسانی می‌گردد و بعد از بررسی‌های لازم مستند یک نسخه جدید از مستند با افزایش شماره نسخه منتشر می‌گردد. برای دیدن انتشار‌های فعلی مستند می‌تواند به [بخش انتشار‌ها](https://github.com/BSVN/CppCoreGuidelines/releases) مراجعه کنید.

Many of the guidelines make use of the header-only Guideline Support Library. One implementation is available at [GSL: Guideline Support Library](https://github.com/Microsoft/GSL).

## Background and scope

The aim of the guidelines is to help people to use modern C++ effectively. By "modern C++" we mean C++11 and C++14 (and soon C++17). In other
words, what would you like your code to look like in 5 years' time, given that you can start now? In 10 years' time?

The guidelines are focused on relatively higher-level issues, such as interfaces, resource management, memory management, and concurrency. Such
rules affect application architecture and library design. Following the rules will lead to code that is statically type-safe, has no resource
leaks, and catches many more programming logic errors than is common in code today. And it will run fast -- you can afford to do things right.

We are less concerned with low-level issues, such as naming conventions and indentation style. However, no topic that can help a programmer is
out of bounds.

Our initial set of rules emphasizes safety (of various forms) and simplicity. They may very well be too strict. We expect to have to introduce
more exceptions to better accommodate real-world needs. We also need more rules.

You will find some of the rules contrary to your expectations or even contrary to your experience. If we haven't suggested that you change your
coding style in any way, we have failed! Please try to verify or disprove rules! In particular, we'd really like to have some of our rules
backed up with measurements or better examples.

You will find some of the rules obvious or even trivial. Please remember that one purpose of a guideline is to help someone who is less
experienced or coming from a different background or language to get up to speed.

The rules are designed to be supported by an analysis tool. Violations of rules will be flagged with references (or links) to the relevant rule.
We do not expect you to memorize all the rules before trying to write code.

The rules are meant for gradual introduction into a code base. We plan to build tools for that and hope others will too.

## Contributions and LICENSE

Comments and suggestions for improvements are most welcome. We plan to modify and extend this document as our understanding improves and the
language and the set of available libraries improve. More details are found at [CONTRIBUTING](./CONTRIBUTING.md) and [LICENSE](./LICENSE) .
