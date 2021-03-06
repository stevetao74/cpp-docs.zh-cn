---
title: strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l
ms.date: 11/04/2016
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
ms.openlocfilehash: b984460d5b87e6a1d195e4127234479f8f7c8b0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649470"
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l

通过使用当前区域设置或传入的指定区域设置，查找在字符串中的下一个标记。 提供这些函数的更多安全版本；请参阅 [strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)。

> [!IMPORTANT]
> **_mbstok**并 **_mbstok_l**不能在 Windows 运行时中执行的应用程序中使用。 有关详细信息，请参阅[通用 Windows 平台应用中不支持的 CRT 函数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)。

## <a name="syntax"></a>语法

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>参数

*strToken*<br/>
包含一个或多个标记的字符串。

*strDelimit*<br/>
分隔符字符组。

*locale*<br/>
要使用的区域设置。

## <a name="return-value"></a>返回值

返回一个指向下一个令牌中找到*strToken*。 它们将返回**NULL**找到没有更多标记时。 每个调用都会修改*strToken* ，只需替换 null 字符在返回的令牌后发生的第一个分隔符。

## <a name="remarks"></a>备注

**Strtok**函数查找字符串中的下一个标记*strToken*。 中的字符组*strDelimit*指定的令牌中找到可能的分隔符*strToken*在当前调用上。 **wcstok**并 **_mbstok**宽字符及多字节字符版本的**strtok**。 参数和返回值**wcstok**是宽字符字符串; **_mbstok**是多字节字符字符串。 否则这三个函数否则具有相同行为。

> [!IMPORTANT]
> 这些函数会引发由缓冲区溢出问题带来的潜在威胁。 缓冲区溢出问题是常见的系统攻击方法，使权限的提升不能确保。 有关详细信息，请参阅 [避免缓冲区溢出](/windows/desktop/SecBP/avoiding-buffer-overruns)。

在首次调用**strtok**，函数跳过前导分隔符并返回一个指针中的第一个标记*strToken*，终止空字符的标记。 更多标记可以分离出的余数*strToken*的调用的一系列**strtok**。 每次调用**strtok**修改*strToken*的方法是插入 null 字符之后**令牌**通过调用返回。 若要读取的下一个令牌*strToken*，调用**strtok**与**NULL**值*strToken*参数。 **NULL** *strToken*参数可以使**strtok**搜索中的修改后的下一个标记*strToken*。 *StrDelimit*参数可使用从到下一次调用的任何值，以使分隔符集可能会有所不同。

输出值受区域设置的 LC_CTYPE 类别设置影响；有关详细信息，请参阅 [setlocale](setlocale-wsetlocale.md)。 这些不带 **_l** 后缀的函数版本使用此区域设置相关的行为的当前区域设置；带有 **_l** 后缀的版本相同，只不过它们使用传递的区域设置参数。 有关详细信息，请参阅 [Locale](../../c-runtime-library/locale.md)。

> [!NOTE]
> 每个函数均使用线程本地静态变量，以将字符串分析为标记。 因此，多线程可以同时调用这些函数，不会产生不良影响。 但是，在单个线程内，对任一这些函数的交替调用很可能导致数据损坏和结果不准确。 解析不同的字符串时，在解析完一个字符串后再开始解析下一个字符串。 此外，请注意，从调用其他函数的循环内调用其中任一函数可能引发潜在危险。 如果其他函数最终使用这些函数之一，则导致调用交错的序列，从而触发数据损坏。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|TCHAR.H 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**_tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**strtok**|\<string.h>|
|**wcstok**|\<string.h> 或 \<wchar.h>|
|**_mbstok**， **_mbstok_l**|\<mbstring.h>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_strtok.c
// compile with: /W3
// In this program, a loop uses strtok
// to print all the tokens (separated by commas
// or blanks) in the string named "string".
//
#include <string.h>
#include <stdio.h>

char string[] = "A string\tof ,,tokens\nand some  more tokens";
char seps[]   = " ,\t\n";
char *token;

int main( void )
{
   printf( "Tokens:\n" );

   // Establish string and get the first token:
   token = strtok( string, seps ); // C4996
   // Note: strtok is deprecated; consider using strtok_s instead
   while( token != NULL )
   {
      // While there are tokens in "string"
      printf( " %s\n", token );

      // Get next token:
      token = strtok( NULL, seps ); // C4996
   }
}
```

```Output
Tokens:
A
string
of
tokens
and
some
more
tokens
```

## <a name="see-also"></a>请参阅

[字符串操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[区域设置](../../c-runtime-library/locale.md)<br/>
[多字节字符序列的解释](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn、wcscspn、_mbscspn、_mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
