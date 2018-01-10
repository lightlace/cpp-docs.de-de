---
title: Mit der Bezeichnung Anweisungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 139b94ab0287de5449e0b03ca96f5443049cfb5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="labeled-statements"></a>Anweisungen mit Bezeichnung
Bezeichnungen werden verwendet, um die Programmsteuerung direkt an die angegebene Anweisung zu übertragen.  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 Der Umfang einer Bezeichnung ist die gesamte Funktion, in der diese deklariert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Es gibt drei Typen von bezeichneten Anweisungen. Alle verwenden einen Doppelpunkt, um einen Bezeichnungstyp von der Anweisung zu trennen. Die case- und default-Bezeichnungen sind für case-Anweisungen bestimmt.  
  
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
  
 **Die Goto-Anweisung**  
  
 Die Darstellung einer *Bezeichner* -Bezeichnung im Quellprogramm deklariert eine Bezeichnung. Nur eine [Goto](../cpp/goto-statement-cpp.md) Anweisung kann übertragen Sie die Steuerung an eine *Bezeichner* Bezeichnung. Das folgende Codefragment veranschaulicht die Verwendung von der `goto` Anweisung und eine *Bezeichner* Bezeichnung:  
  
 Eine Bezeichnung kann nicht allein stehen, sondern muss immer an eine Anweisung angefügt werden. Wenn eine Bezeichnung allein benötigt wird, platzieren Sie nach ihr eine NULL-Anweisung.  
  
 Die Bezeichnung gilt funktionsweit und kann nicht innerhalb der Funktion erneut deklariert werden. Allerdings kann derselbe Name in verschiedenen Funktionen als Bezeichnung verwendet werden.  
  
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
  
 **Der Case-Anweisung**  
  
 Bezeichnungen, die nach Auftreten der **Fall** Schlüsselwort kann nicht auch außerhalb der angezeigt werden. eine `switch` Anweisung. (Diese Einschränkung gilt auch für die **Standard** Schlüsselwort.) Das folgende Codefragment zeigt die korrekte Verwendung von **Fall** Bezeichnungen:  
  
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
  
## <a name="labels-in-the-case-statement"></a>Bezeichnungen in der case-Anweisung  
 Bezeichnungen, die nach Auftreten der **Fall** Schlüsselwort kann nicht auch außerhalb der angezeigt werden. eine `switch` Anweisung. (Diese Einschränkung gilt auch für die **Standard** Schlüsselwort.) Das folgende Codefragment zeigt die korrekte Verwendung von **Fall** Bezeichnungen:  
  
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
  
## <a name="labels-in-the-goto-statement"></a>Bezeichnungen in der goto-Anweisung  
 Die Darstellung einer *Bezeichner* -Bezeichnung im Quellprogramm deklariert eine Bezeichnung. Nur eine [Goto](../cpp/goto-statement-cpp.md) Anweisung kann übertragen Sie die Steuerung an eine *Bezeichner* Bezeichnung. Das folgende Codefragment veranschaulicht die Verwendung von der `goto` Anweisung und eine *Bezeichner* Bezeichnung:  
  
 Eine Bezeichnung kann nicht allein stehen, sondern muss immer an eine Anweisung angefügt werden. Wenn eine Bezeichnung allein benötigt wird, platzieren Sie nach ihr eine NULL-Anweisung.  
  
 Die Bezeichnung gilt funktionsweit und kann nicht innerhalb der Funktion erneut deklariert werden. Allerdings kann derselbe Name in verschiedenen Funktionen als Bezeichnung verwendet werden.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über C++-Anweisungen](../cpp/overview-of-cpp-statements.md)   
 [switch-Anweisung (C++)](../cpp/switch-statement-cpp.md)