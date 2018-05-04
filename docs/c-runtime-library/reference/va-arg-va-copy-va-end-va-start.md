---
title: va_arg, va_copy, va_end, va_start | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- va_arg
- va_end
- va_copy
- va_start
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
apitype: DLLExport
f1_keywords:
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f634e713bcf87aa6d97ed4e49595e4c0f8b72ab3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="vaarg-vacopy-vaend-vastart"></a>va_arg, va_copy, va_end, va_start

Greift auf Variablenargumentelisten zu.

## <a name="syntax"></a>Syntax

```C
type va_arg(
   va_list arg_ptr,
   type
);
void va_copy(
   va_list dest,
   va_list src
); // (ISO C99 and later)
void va_end(
   va_list arg_ptr
);
void va_start(
   va_list arg_ptr,
   prev_param
); // (ANSI C89 and later)
void va_start(
   arg_ptr
);  // (deprecated Pre-ANSI C89 standardization version)
```

### <a name="parameters"></a>Parameter

*Typ*<br/>
Typ des abzurufenden Arguments.

*arg_ptr*<br/>
Zeiger auf die Liste der Argumente.

*dest*<br/>
Zeiger auf die Liste von Argumenten, die vom initialisierenden *Src*

*src*<br/>
Zeiger auf die initialisierte Liste von Argumenten, die zum Kopieren *Dest*.

*prev_param*<br/>
Parameter, der dem ersten optionalen Argument vorausgeht.

## <a name="return-value"></a>Rückgabewert

**Va_arg** gibt das aktuelle Argument zurück. **Va_copy**, **Va_start** und **Va_end** geben keine Werte zurück.

## <a name="remarks"></a>Hinweise

Die **Va_arg**, **Va_copy**, **Va_end**, und **Va_start** Makros ermöglichen auf portierbare Weise auf die Argumente für eine Funktion bei der Funktion akzeptiert eine Variable Anzahl von Argumenten. Es gibt zwei Versionen der Makros: Die in STDARG.H definierten Makros, die mit dem ISO-Standard C99 konform sind, und die in VARARGS.H definierten Makros, die zwar als veraltet markiert sind, aber beibehalten werden, da sie für Code abwärts kompatibel sind, der vor dem ANSI-Standard C89 geschrieben wurde.

Diese Makros setzen voraus, dass die Funktion eine feste Anzahl von erforderlichen Argumenten akzeptiert, gefolgt von einer variablen Anzahl von optionalen Argumenten. Die erforderlichen Argumente werden als gewöhnliche Parameter für die Funktion deklariert und können über die Parameternamen aufgerufen werden. Die optionalen Argumente werden über Makros in STDARG.H (oder in VARARGS.H für Code, der vor dem ANSI-Standard C89 geschrieben wurde) aufgerufen, wodurch ein Zeiger auf das erste optionale Argument in der Argumentliste festgelegt wird und zurückgesetzt wird, nachdem das Verarbeiten der Argumente abgeschlossen ist.

Die in STDARG.H definierten C-Standardmakros werden wie folgt verwendet:

- **Va_start** legt *Arg_ptr* auf das erste optionale Argument in der Liste der Argumente, die an die Funktion übergeben wird. Das Argument *Arg_ptr* benötigen die **Va_list** Typ. Das Argument *Prev_param* ist der Name des erforderlichen Parameters, der das erste optionale Argument in der Argumentliste direkt vorausgeht. Wenn *Prev_param* deklariert mit der registerspeicherklasse Verhalten für das Makro ist nicht definiert ist. **Va_start** muss verwendet werden, bevor **Va_arg** zum ersten Mal verwendet wird.

- **Va_arg** Ruft den Wert eines *Typ* aus dem die vom angegebenen Speicherort *Arg_ptr*, und inkrementiert *Arg_ptr* , zeigen Sie auf das folgende Argument in der Liste von Mithilfe des Umfangs der *Typ* um zu bestimmen, wo das folgende Argument beginnt. **Va_arg** kann oft in der Funktion verwendet, um Argumente aus der Liste abzurufen.

- **Va_copy** erstellt eine Kopie einer Liste von Argumenten im aktuellen Zustand. Die *Src* Parameter muss bereits mit initialisiert werden **Va_start**; er wurde möglicherweise mit aktualisiert **Va_arg** aufruft, jedoch muss nicht zurückgesetzt wurden mit **Va_end** . Das folgende Argument, das durch abgerufenen **Va_arg** aus *Dest* ist identisch mit dem folgenden Argument, die aus abgerufen *Src*.

- Nach dem Abruf aller Argumente **Va_end** setzt den Zeiger auf **NULL**. **Va_end** muss aufgerufen werden, auf jeder Argumentliste, die mit initialisiert wird **Va_start** oder **Va_copy** vor der Rückkehr der Funktion.

> [!NOTE]
> Die in VARARGS.H definierten Makros sind als veraltet markiert und werden nur beibehalten, weil sie für Code abwärts kompatibel sind, der vor dem ANSI-Standard C89 geschrieben wurde. Verwenden Sie in allen anderen Fällen die Makros in STDARGS.H.

Da sie mithilfe von [/clr (CLR-Kompilierung, Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, generieren Programme, die diese Makros verwenden, möglicherweise unerwartete Ergebnisse. Dies liegt an den Unterschieden zwischen nativen und CLR-Typsystemen (Common Language Runtime). Beachten Sie dieses Programm:

```C
#include <stdio.h>
#include <stdarg.h>

void testit (int i, ...)
{
    va_list argptr;
    va_start(argptr, i);

    if (i == 0)
    {
        int n = va_arg(argptr, int);
        printf("%d\n", n);
    }
    else
    {
        char *s = va_arg(argptr, char*);
        printf("%s\n", s);
    }

    va_end(argptr);
}

int main()
{
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int
    testit(1, NULL);       // 2nd problem: NULL is not a char*
}
```

Beachten Sie, dass **Testit** erwartet als zweiten Parameter entweder ein **Int** oder ein **Char\***. Die übergebenen Argumente sind 0xffffffff (ein **ohne Vorzeichen** **Int**, sondern eine **Int**) und **NULL** (tatsächlich ein **Int**, sondern eine **Char\***). Wenn das Programm für nativen Code kompiliert wird, erzeugt es diese Ausgabe:

```Output
-1

(null)
```

## <a name="requirements"></a>Anforderungen

**Header:** \<stdio.h> und \<stdarg.h>

**Veralteter Header:** \<varargs.h>

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_va.c
// Compile with: cl /W3 /Tc crt_va.c
// The program below illustrates passing a variable
// number of arguments using the following macros:
//      va_start            va_arg              va_copy
//      va_end              va_list

#include <stdio.h>
#include <stdarg.h>
#include <math.h>

double deviation(int first, ...);

int main( void )
{
    /* Call with 3 integers (-1 is used as terminator). */
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));

    /* Call with 4 integers. */
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));

    /* Call with just -1 terminator. */
    printf("Deviation is: %f\n", deviation(-1));
}

/* Returns the standard deviation of a variable list of integers. */
double deviation(int first, ...)
{
    int count = 0, i = first;
    double mean = 0.0, sum = 0.0;
    va_list marker;
    va_list copy;

    va_start(marker, first);     /* Initialize variable arguments. */
    va_copy(copy, marker);       /* Copy list for the second pass */
    while (i != -1)
    {
        sum += i;
        count++;
        i = va_arg(marker, int);
    }
    va_end(marker);              /* Reset variable argument list. */
    mean = sum ? (sum / count) : 0.0;

    i = first;                  /* reset to calculate deviation */
    sum = 0.0;
    while (i != -1)
    {
        sum += (i - mean)*(i - mean);
        i = va_arg(copy, int);
    }
    va_end(copy);               /* Reset copy of argument list. */
    return count ? sqrt(sum / count) : 0.0;
}
```

```Output
Deviation is: 0.816497
Deviation is: 2.236068
Deviation is: 0.000000
```

## <a name="see-also"></a>Siehe auch

[Argumentzugriff](../../c-runtime-library/argument-access.md)<br/>
[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)<br/>
