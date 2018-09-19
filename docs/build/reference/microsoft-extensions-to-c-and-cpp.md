---
title: Microsoft-Erweiterungen für C und C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- or_eq operator
- ~ operator, extensions to C/C++
- '& operator, extensions to C/C++'
- '&= operator'
- iso646.h header
- Xor operator, Microsoft extensions to C/C++
- '!= operator'
- '! operator, extension to C++'
- Or operator, Microsoft extensions to C/C++
- ^ operator, extensions to C/C++
- ^= operator, C++ extensions
- xor_eq operator
- and_eq operator
- Microsoft extensions to C/C++
- '|= operator'
- '|| operator'
- And operator, extensions to C/C++
- NOT operator
- '&& operator'
- extensions, C language
- Visual C++, extensions to C/C++
- '| operator, extensions'
- not_eq operator
- Visual C, Microsoft extensions
- extensions
- compl method
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7de81d7611715e906b69f5546fafbcefa3252d64
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722474"
---
# <a name="microsoft-extensions-to-c-and-c"></a>Microsoft-Erweiterungen für C und C++

Visual C++ erweitert die ANSI C- und ANSI C++ Standards wie folgt.

## <a name="keywords"></a>Stichwörter

Es werden mehrere Schlüsselwörter hinzugefügt. In der Liste im [Schlüsselwörter](../../cpp/keywords-cpp.md), die Schlüsselwörter, die zwei führenden unterstrichen sind, Visual C++-Erweiterungen.

## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>Aus der Klassendefinition von static const Integral (oder Enumeration)-Member

Dem Standard (**/Za**), achten Sie eine Definition außerhalb von Klassen für die Datenelemente, wie hier gezeigt:

```cpp
class CMyClass  {
   static const int max = 5;
   int m_array[max];
}
// . . .
const int CMyClass::max;   // out of class definition
```

Klicken Sie unter **/Ze**, die außerhalb der Klasse ist für statische, const integral-Datenmember und const Enum-Datenmember optional. Nur ganze Zahlen und Enumerationen, die als "static" und "const" definiert sind, können innerhalb einer Klasse initialisiert werden; der Initialisierungsausdruck muss ein const-Ausdruck sein.

Um Fehler zu vermeiden, wenn eine Definition außerhalb von Klassen ist, sofern in einem Header und die Headerdatei in mehreren Quelldateien enthalten ist, verwenden Sie [Selectany](../../cpp/selectany.md). Zum Beispiel:

```cpp
__declspec(selectany) const int CMyClass::max = 5;
```

## <a name="casts"></a>Typumwandlungen

Sowohl der C++-Compiler als auch der C-Compiler unterstützen diese Typumwandlungen, die nicht ANSI-konform sind:

- Nicht ANSI-konforme Typumwandlungen zum Erzeugen von l-Werten. Zum Beispiel:

   ```C
   char *p;
   (( int * ) p )++;
   ```

   > [!NOTE]
   > Diese Erweiterung ist nur in der Programmiersprache C verfügbar. Sie können das folgende ANSI C-Standardformular in C++-Code verwenden, um einen Zeiger so zu ändern, als ob es ein Zeiger zu einem anderen Typ ist.

   Das vorherige Beispiel könnte folgendermaßen umgeschrieben werden, um dem ANSI C-Standard zu entsprechen:

   ```C
   p = ( char * )(( int * )p + 1 );
   ```

- Nicht ANSI-konforme Typumwandlung eines Funktionszeigers in einen Datenzeiger. Zum Beispiel:

   ```C
   int ( * pfunc ) ();
   int *pdata;
   pdata = ( int * ) pfunc;
   ```

   Zur Durchführung derselben Typumwandlung unter zusätzlicher Beibehaltung der ANSI-Kompatibilität können Sie den Funktionszeiger in `uintptr_t` umwandeln, bevor sie diesen in einen Datenzeiger umwandeln:

   ```C
   pdata = ( int * ) (uintptr_t) pfunc;
   ```

## <a name="variable-length-argument-lists"></a>Argumentlisten variabler Länge

Sowohl der C++-Compiler als auch der C-Compiler unterstützen einen Funktionsdeklarator, der eine variable Anzahl von Argumenten angibt, gefolgt von einer Funktionsdefinition, die stattdessen einen Typ bereitstellt:

```cpp
void myfunc( int x, ... );
void myfunc( int x, char * c )
{ }
```

## <a name="single-line-comments"></a>Einzeilige Kommentare

Der C-Compiler unterstützt einzeilige Kommentare, die mit zwei Schrägstrichen (//) eingeleitet werden:

```C
// This is a single-line comment.
```

## <a name="scope"></a>Bereich

Der C-Compiler unterstützt bezogen auf den Gültigkeitsbereich die folgenden Funktionen:

- Neudefinition von extern-Elementen als "static":

   ```C
   extern int clip();
   static int clip()
   {}
   ```

- Verwendung von typedef-Neudefinitionen ohne Auswirkung innerhalb desselben Gültigkeitsbereichs:

   ```C
   typedef int INT;
   typedef int INT;
   ```

- Funktionsdeklaratoren haben einen Dateigültigkeitsbereich:

   ```C
   void func1()
   {
       extern int func2( double );
   }
   int main( void )
   {
       func2( 4 );    //  /Ze passes 4 as type double
   }                  //  /Za passes 4 as type int
   ```

- Verwendung von Blockbereichsvariablen, die durch nicht konstante Ausdrücke initialisiert werden:

   ```C
   int clip( int );
   int bar( int );
   int main( void )
   {
       int array[2] = { clip( 2 ), bar( 4 ) };
   }
   int clip( int x )
   {
       return x;
   }
   int bar( int x )
   {
       return x;
   }
   ```

## <a name="data-declarations-and-definitions"></a>Datendeklarationen und-Definitionen

Der C-Compiler unterstützt die folgenden Datendeklarations- und Datendefinitionsfunktionen:

- Gemischte Zeichen- und Zeichenfolgenkonstanten in einer Initialisierung:

   ```C
   char arr[5] = {'a', 'b', "cde"};
   ```

- Bitfelder, die Basistypen aufweisen **ganze Zahl ohne Vorzeichen** oder **signiert Int**.

- Deklaratoren, die keinen Typ haben:

   ```C
   x;
   int main( void )
   {
       x = 1;
   }
   ```

- Arrays ohne Größenangabe als letztes Feld in Strukturen und Unions:

   ```C
   struct zero
   {
       char *c;
       int zarray[];
   };
   ```

- Unbenannte (anonyme) Strukturen:

   ```C
   struct
   {
       int i;
       char *s;
   };
   ```

- Unbenannte (anonyme) Unions:

   ```C
   union
   {
       int i;
       float fl;
   };
   ```

- Unbenannte Member:

   ```C
   struct s
   {
      unsigned int flag : 1;
      unsigned int : 31;
   }
   ```

## <a name="intrinsic-floating-point-functions"></a>Systeminterne Gleitkommafunktionen

Sowohl die X86 C++-Compiler und C-Compiler unterstützen die Inlinegenerierung der der `atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt`, und `tan` Funktionen bei der **/Oi** angegeben ist. Beim C-Compiler geht die ANSI-Konformität verloren, wenn diese systeminternen Funktionen verwendet werden, da die `errno`-Variable von ihnen nicht festgelegt wird.

## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Übergabe von einem nicht Konstanten Zeigerparameters an eine Funktion, die erwartet einen Verweis auf einen Konstanten Zeigerparameter

Dies ist eine Erweiterung von C++. Dieser Code erfolgt die Kompilierung mit **/Ze**:

```cpp
typedef   int   T;

const T  acT = 9;      // A constant of type 'T'
const T* pcT = &acT;   // A pointer to a constant of type 'T'

void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'
{
   rpcT = pcT;
}

T*   pT;               // A pointer to a 'T'

void func ()
{
   func2 ( pT );      // Should be an error, but isn't detected
   *pT   = 7;         // Invalidly overwrites the constant 'acT'
}
```

## <a name="iso646h-not-enabled"></a>ISO646. H nicht aktiviert

Klicken Sie unter **/Ze**, müssen Sie iso646.h einschließen, wenn Sie die Textformen der folgenden Operatoren verwenden möchten:

- && (and)

- &= (and_eq)

- & (bitand)

- &#124;(Bitor)

- ~ (compl)

- ! (not)

- != (not_eq)

- &#124;&#124;(oder)

- &#124;= (Or_eq)

- ^ (xor)

- ^= (xor_eq)

## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>Die Adresse eines Zeichenfolgenliterals hat Typ const Char [], nicht const Char (*)]

Im folgende Beispiel wird Ausgabe `char const (*)[4]` unter **/Za**, aber `char const [4]` unter **/Ze**.

```cpp
#include <stdio.h>
#include <typeinfo>

int main()
{
    printf_s("%s\n", typeid(&"abc").name());
}
```

## <a name="see-also"></a>Siehe auch

- [/Za, /Ze (Spracherweiterungen deaktivieren)](../../build/reference/za-ze-disable-language-extensions.md)
- [Compileroptionen](../../build/reference/compiler-options.md)
- [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
