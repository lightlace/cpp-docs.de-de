---
title: "Anweisungen mit Bezeichnung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "goto"
  - "case"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anweisung mit Bezeichnung"
  - "Anweisungen, Mit Bezeichnung"
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Anweisungen mit Bezeichnung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bezeichnungen werden verwendet, um die Programmsteuerung direkt an die angegebene Anweisung zu übertragen.  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 Der Umfang einer Bezeichnung ist die gesamte Funktion, in der diese deklariert wurde.  
  
## Hinweise  
 Es gibt drei Typen von bezeichneten Anweisungen.  Alle verwenden einen Doppelpunkt, um einen Bezeichnungstyp von der Anweisung zu trennen.  Die case\- und default\-Bezeichnungen sind für case\-Anweisungen bestimmt.  
  
```cpp  
#include <iostream>   
using namespace std;   
  
void test_label(int x) {  
  
    if (x == 1){  
        goto label1;  
    }  
    goto label2;  
  
label1:  
    cout << "in label1" << endl;  
    return;  
  
label2:  
    cout << "in label2" << endl;  
    return;  
}  
  
int main() {  
    test_label(1);  // in label1   
    test_label(2);  // in label2  
}  
  
```  
  
 **Die goto\-Anweisung**  
  
 Eine *identifier*\-Bezeichnung im Quellprogramm deklariert eine Bezeichnung.  Nur eine [goto](../cpp/goto-statement-cpp.md)\-Anweisung kann die Steuerung an eine *identifier*\-Bezeichnung übergeben.  Das folgende Codefragment zeigt die Verwendung der `goto`\-Anweisung und einer *identifier*\-Bezeichnung:  
  
 Eine Bezeichnung kann nicht allein stehen, sondern muss immer an eine Anweisung angefügt werden.  Wenn eine Bezeichnung allein benötigt wird, platzieren Sie nach ihr eine NULL\-Anweisung.  
  
 Die Bezeichnung gilt funktionsweit und kann nicht innerhalb der Funktion erneut deklariert werden.  Allerdings kann derselbe Name in verschiedenen Funktionen als Bezeichnung verwendet werden.  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
}  
  
//Output: At Test2 label.  
```  
  
 **Die case\-Anweisung**  
  
 Bezeichnungen, die nach dem **case**\-Schlüsselwort angezeigt werden, können nicht ebenfalls außerhalb einer `switch`\-Anweisung angezeigt werden.  \(Diese Einschränkung gilt auch für das **default**\-Schlüsselwort.\) Folgendes Codefragment zeigt die korrekte Verwendung von **case**\-Bezeichnungen:  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );   
      EndPaint( hWnd, &ps );  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## Bezeichnungen in der case\-Anweisung  
 Bezeichnungen, die nach dem **case**\-Schlüsselwort angezeigt werden, können nicht ebenfalls außerhalb einer `switch`\-Anweisung angezeigt werden.  \(Diese Einschränkung gilt auch für das **default**\-Schlüsselwort.\) Folgendes Codefragment zeigt die korrekte Verwendung von **case**\-Bezeichnungen:  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      // Obtain a handle to the device context.  
      // BeginPaint will send WM_ERASEBKGND if appropriate.  
  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );  
  
      // Inform Windows that painting is complete.  
  
      EndPaint( hWnd, &ps );  
      break;  
  
   case WM_CLOSE:  
      // Close this window and all child windows.  
  
      KillTimer( hWnd, TIMER1 );  
      DestroyWindow( hWnd );  
      if ( hWnd == hWndMain )  
         PostQuitMessage( 0 );  // Quit the application.  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## Bezeichnungen in der goto\-Anweisung  
 Eine *identifier*\-Bezeichnung im Quellprogramm deklariert eine Bezeichnung.  Nur eine [goto](../cpp/goto-statement-cpp.md)\-Anweisung kann die Steuerung an eine *identifier*\-Bezeichnung übergeben.  Das folgende Codefragment zeigt die Verwendung der `goto`\-Anweisung und einer *identifier*\-Bezeichnung:  
  
 Eine Bezeichnung kann nicht allein stehen, sondern muss immer an eine Anweisung angefügt werden.  Wenn eine Bezeichnung allein benötigt wird, platzieren Sie nach ihr eine NULL\-Anweisung.  
  
 Die Bezeichnung gilt funktionsweit und kann nicht innerhalb der Funktion erneut deklariert werden.  Allerdings kann derselbe Name in verschiedenen Funktionen als Bezeichnung verwendet werden.  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
// At Test2 label.  
}  
  
```  
  
## Siehe auch  
 [Übersicht über C\+\+\-Anweisungen](../cpp/overview-of-cpp-statements.md)   
 [switch\-Anweisung \(C\+\+\)](../cpp/switch-statement-cpp.md)