---
title: "Namen ohne Verkn&#252;pfung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Enumeratoren [C++], Verknüpfung"
  - "Funktionsparameter [C++]"
  - "Funktionen [C++], Parameter"
  - "Namen [C++], Ohne Verknüpfung"
  - "typedef-Namen, Verknüpfung"
ms.assetid: 7174c500-12d2-4572-8c16-63c27c758fb1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Namen ohne Verkn&#252;pfung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die einzigen Namen ohne Bindung sind:  
  
-   Funktionsparameter  
  
-   Namen mit Blockgültigkeit, die nicht als `extern` oder **static** deklariert sind  
  
-   Enumeratoren  
  
-   Namen, die in einer `typedef`\-Anweisung deklariert werden.  Eine Ausnahme ist, wenn die `typedef`\-Anweisung verwendet wird, um einen Namen für einen nicht benannten Klassentyp anzugeben.  Wenn die Klasse über eine externe Bindung verfügt, kann der Name ebenfalls eine externe Bindung aufweisen.  Das folgende Beispiel zeigt eine Situation, in der ein `typedef`\-Name eine externe Bindung hat:  
  
    ```  
    // names_with_no_linkage.cpp  
    typedef struct  
    {  
       short x;  
       short y;  
    } POINT;  
  
    extern int MoveTo( POINT pt );  
  
    int main()  
    {  
    }  
    ```  
  
     Der `typedef`\-Name, `POINT`, wird der Klassenname für die unbenannte Struktur.  Er wird anschließend verwendet, um eine Funktion mit externer Bindung zu deklarieren.  
  
 Da `typedef`\-Namen keine Bindung haben, können sich ihre Definitionen zwischen Übersetzungseinheiten unterscheiden.  Da die Kompilierungen getrennt stattfinden, gibt es keine Möglichkeit für den Compiler, diese Unterschiede festzustellen.  Daher werden Fehler dieser Art erst zur Verknüpfungszeit erkannt.  Betrachten Sie folgenden Fall:  
  
```  
// Translation unit 1  
typedef int INT  
  
INT myInt;  
...  
  
// Translation unit 2  
typedef short INT  
  
extern INT myInt;  
...  
```  
  
 Der vorhergehende Code generiert einen "nicht aufgelösten externen" Fehler zur Verknüpfungszeit.  
  
## Beispiel  
 C\+\+\-Funktionen können nur im Gültigkeitsbereich der Datei oder der Klasse definiert werden.  Das folgende Beispiel veranschaulicht, wie Sie Funktionen definieren, und es zeigt eine fehlerhafte Funktionsdefinition:  
  
```  
// function_definitions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
void ShowChar( char ch );    // Declare function ShowChar.  
  
void ShowChar( char ch )     // Define function ShowChar.  
{                            // Function has file scope.  
   cout << ch;  
}  
  
struct Char                  // Define class Char.  
{  
    char Show();             // Declare Show function.  
    char Get();              // Declare Get function.  
    char ch;  
};  
  
char Char::Show()            // Define Show function  
{                            //  with class scope.  
    cout << ch;  
    return ch;  
}  
  
void GoodFuncDef( char ch )  // Define GoodFuncDef  
{                            //  with file scope.  
    int BadFuncDef( int i )  // C2601, Erroneous attempt to  
    {                        //  nest functions.  
        return i * 7;  
    }  
    for( int i = 0; i < BadFuncDef( 2 ); ++i )  
        cout << ch;  
    cout << "\n";  
}  
```  
  
## Siehe auch  
 [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md)