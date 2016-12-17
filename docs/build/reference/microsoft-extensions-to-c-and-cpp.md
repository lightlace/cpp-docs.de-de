---
title: "Microsoft-Erweiterungen f&#252;r C und C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! Operator, Erweiterungen von C++"
  - "!=-Operator"
  - "& (Operator), Erweiterungen von C/C++"
  - "&&-Operator"
  - "&= (Operator)"
  - "^-Operator, Erweiterungen von C/C++"
  - "^= (Operator), C++-Erweiterungen"
  - "| (Operator), Erweiterungen"
  - "||-Operator"
  - "|= (Operator)"
  - "~ (Operator), Erweiterungen von C/C++"
  - "And-Operator, Erweiterungen von C/C++"
  - "and_eq-Operator"
  - "compl-Methode"
  - "Erweiterungen"
  - "Erweiterungen, C-Sprache"
  - "iso646.h-Header"
  - "Microsoft-Erweiterungen für C/C++"
  - "NOT-Operator"
  - "not_eq-Operator"
  - "Or-Operator, Microsoft-Erweiterungen für C/C++"
  - "or_eq-Operator"
  - "Visual C, Microsoft-Erweiterungen"
  - "Visual C++, Erweiterungen von C/C++"
  - "Xor-Operator, Microsoft-Erweiterungen für C/C++"
  - "xor_eq-Operator"
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# Microsoft-Erweiterungen f&#252;r C und C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ erweitert die ANSI C\- und ANSI C\+\+ Standards wie folgt.  
  
## Schlüsselwörter  
 Es werden mehrere Schlüsselwörter hinzugefügt.  Die Schlüsselwörter mit zwei führenden Unterstrichen in der Liste in [C\+\+\-Schlüsselwörter](../../cpp/keywords-cpp.md) sind Visual C\+\+\-Erweiterungen.  
  
## Definition der Member "static", "const integral" und "const enum" außerhalb von Klassen  
 Dem Standard entsprechend \(**\/Za**\) müssen Sie für Datenmember eine Definition außerhalb von Klassen vornehmen, wie hier gezeigt:  
  
```  
class CMyClass  {  
   static const int max = 5;  
   int m_array[max];  
}  
...  
const int CMyClass::max;   // out of class definition  
```  
  
 Unter **\/Ze** ist die Definition außerhalb von Klassen für static\-Datenmember, const integral\-Datenmember und const enum\-Datenmember optional.  Nur ganze Zahlen und Enumerationen, die als "static" und "const" definiert sind, können innerhalb einer Klasse initialisiert werden; der Initialisierungsausdruck muss ein const\-Ausdruck sein.  
  
 Um Fehler zu vermeiden, wenn eine Definition außerhalb von Klassen in einer Headerdatei bereitgestellt wird und die Headerdatei in mehreren Quelldateien enthalten ist, verwenden Sie [selectany](../../cpp/selectany.md).  Beispiel:  
  
```  
__declspec(selectany) const int CMyClass::max = 5;  
```  
  
## Typumwandlungen  
 Sowohl der C\+\+\-Compiler als auch der C\-Compiler unterstützen diese Typumwandlungen, die nicht ANSI\-konform sind:  
  
-   Nicht ANSI\-konforme Typumwandlungen zum Erzeugen von l\-Werten.  Beispiel:  
  
    ```  
    char *p;  
    (( int * ) p )++;  
    ```  
  
    > [!NOTE]
    >  Diese Erweiterung ist nur in der Programmiersprache C verfügbar.  Sie können das folgende ANSI C\-Standardformular in C\+\+\-Code verwenden, um einen Zeiger so zu ändern, als ob es ein Zeiger zu einem anderen Typ ist.  
  
     Das vorherige Beispiel könnte folgendermaßen umgeschrieben werden, um dem ANSI C\-Standard zu entsprechen:  
  
    ```  
    p = ( char * )(( int * )p + 1 );  
    ```  
  
-   Nicht ANSI\-konforme Typumwandlung eines Funktionszeigers in einen Datenzeiger.  Beispiel:  
  
    ```  
    int ( * pfunc ) ();   
    int *pdata;  
    pdata = ( int * ) pfunc;  
    ```  
  
     Zur Durchführung derselben Typumwandlung unter zusätzlicher Beibehaltung der ANSI\-Kompatibilität können Sie den Funktionszeiger in `uintptr_t` umwandeln, bevor sie diesen in einen Datenzeiger umwandeln:  
  
    ```  
    pdata = ( int * ) (uintptr_t) pfunc;  
    ```  
  
## Argumentlisten variabler Länge  
 Sowohl der C\+\+\-Compiler als auch der C\-Compiler unterstützen einen Funktionsdeklarator, der eine variable Anzahl von Argumenten angibt, gefolgt von einer Funktionsdefinition, die stattdessen einen Typ bereitstellt:  
  
```  
void myfunc( int x, ... );  
void myfunc( int x, char * c )  
{ }  
```  
  
## Einzeilige Kommentare  
 Der C\-Compiler unterstützt einzeilige Kommentare, die mit zwei Schrägstrichen \(\/\/\) eingeleitet werden:  
  
```  
// This is a single-line comment.  
```  
  
## Umfang  
 Der C\-Compiler unterstützt bezogen auf den Gültigkeitsbereich die folgenden Funktionen:  
  
-   Neudefinition von extern\-Elementen als "static":  
  
    ```  
    extern int clip();  
    static int clip()  
    {}  
    ```  
  
-   Verwendung von typedef\-Neudefinitionen ohne Auswirkung innerhalb desselben Gültigkeitsbereichs:  
  
    ```  
    typedef int INT;  
    typedef int INT;  
    ```  
  
-   Funktionsdeklaratoren haben einen Dateigültigkeitsbereich:  
  
    ```  
    void func1()  
    {  
        extern int func2( double );  
    }  
    int main( void )  
    {  
        func2( 4 );    //  /Ze passes 4 as type double  
    }                  //  /Za passes 4 as type int  
    ```  
  
-   Verwendung von Blockbereichsvariablen, die durch nicht konstante Ausdrücke initialisiert werden:  
  
    ```  
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
  
## Datendeklarationen und \-definitionen  
 Der C\-Compiler unterstützt die folgenden Datendeklarations\- und \-definitionsfunktionen:  
  
-   Gemischte Zeichen\- und Zeichenfolgenkonstanten in einer Initialisierung:  
  
    ```  
    char arr[5] = {'a', 'b', "cde"};  
    ```  
  
-   Bitfelder, die andere Basistypen als **unsigned int** oder **signed int** haben.  
  
-   Deklaratoren, die keinen Typ haben:  
  
    ```  
    x;  
    int main( void )  
    {  
        x = 1;  
    }  
    ```  
  
-   Arrays ohne Größenangabe als letztes Feld in Strukturen und Unions:  
  
    ```  
    struct zero  
    {  
        char *c;  
        int zarray[];  
    };  
    ```  
  
-   Unbenannte \(anonyme\) Strukturen:  
  
    ```  
    struct  
    {  
        int i;  
        char *s;  
    };  
    ```  
  
-   Unbenannte \(anonyme\) Unions:  
  
    ```  
    union  
    {  
        int i;  
        float fl;  
    };  
    ```  
  
-   Unbenannte Member:  
  
    ```  
    struct s  
    {  
       unsigned int flag : 1;  
       unsigned int : 31;  
    }  
    ```  
  
## Systeminterne Gleitkommafunktionen  
 Sowohl der C\+\+\-Compiler als auch der C\-Compiler unterstützen die Inlinegenerierung der folgenden Funktionen – **x86\-spezifisch \>**`atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt` und `tan`; **END x86\-spezifisch**, wenn **\/Oi** angegeben wird.  Beim C\-Compiler geht die ANSI\-Konformität verloren, wenn diese systeminternen Funktionen verwendet werden, da die `errno`\-Variable von ihnen nicht festgelegt wird.  
  
## Übergeben eines nicht konstanten Zeigerparameters an eine Funktion, die einen Verweis auf einen "const"\-Zeigerparameter erwartet  
 Dies ist eine Erweiterung von C\+\+.  Dieser Code wird mit **\/Ze** kompiliert:  
  
```  
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
  
## ISO646.H nicht aktiviert  
 Unter **\/Ze** müssen Sie iso646.h einschließen, wenn Sie die Textformen der folgenden Operatoren verwenden möchten:  
  
-   && \(and\)  
  
-   &\= \(and\_eq\)  
  
-   & \(bitand\)  
  
-   &#124; \(bitor\)  
  
-   ~ \(compl\)  
  
-   \! \(not\)  
  
-   \!\= \(not\_eq\)  
  
-   &#124;&#124; \(or\)  
  
-   &#124;\= \(or\_eq\)  
  
-   ^ \(xor\)  
  
-   ^\= \(xor\_eq\)  
  
## Die Adresse eines Zeichenfolgenliterals hat den Typ "const char \[\]" und nicht "const char \(\*\) \[\]"  
 Im folgenden Beispiel wird bei Verwendung von **\/Za** "char const \(\*\)\[4\]", bei Verwendung von **\/Ze** jedoch "char const \[4\]" ausgegeben.  
  
```  
#include <stdio.h>  
#include <typeinfo>  
  
int main()  
{  
    printf_s("%s\n", typeid(&"abc").name());  
}  
```  
  
## Siehe auch  
 [\/Za, \/Ze \(Spracherweiterungen deaktivieren\)](../../build/reference/za-ze-disable-language-extensions.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)