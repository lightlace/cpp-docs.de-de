---
title: Importieren von Funktionsaufrufen mithilfe von "__declspec(dllimport)" "| Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5553bd5e9999a4737dc258358402eb71269b9c40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="importing-function-calls-using-declspecdllimport"></a>Importieren von Funktionsaufrufen mithilfe von "__declspec(dllimport)"
Im folgenden Codebeispiel wird veranschaulicht, wie **_declspec(dllimport)** Funktionsaufrufe aus einer DLL in eine Anwendung importieren. Angenommen, `func1` ist eine Funktion, die in eine DLL, die getrennt von der .exe-Datei befindet, die enthält die **main** Funktion.  
  
 Ohne **von "__declspec(dllimport)" "**, erhält dieser Code:  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 der Compiler generiert Code, der wie folgt aussieht:  
  
```  
call func1  
```  
  
 und der Linker übersetzt den Aufruf in etwa so aussehen:  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 Wenn `func1` vorhanden ist in eine andere DLL der Linker kann nicht direkt diesem aufgelöst werden, da es keine Möglichkeit, zu wissen, welche die Adresse des wurde `func1` ist. In 16-Bit-Umgebungen fügt der Linker diese Codeadresse auf eine Liste in der .exe-Datei, die das Ladeprogramm zur Laufzeit mit der richtigen Adresse patch würde. In 32-Bit und 64-Bit-Umgebungen generiert der Linker einen Thunk, von dem sie die Adresse kennt. In einer 32-Bit-Umgebung wird der Thunk sieht:  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 Hier `imp_func1` ist die Adresse für die `func1` Slot in der Tabelle der .exe-Datei importieren. Alle Adressen werden daher an den Linker bezeichnet. Das Ladeprogramm muss nur beim Aktualisieren von Importadresstabelle .exe-Datei zur Ladezeit für alles ordnungsgemäß funktioniert.  
  
 Verwenden Sie deshalb **von "__declspec(dllimport)" "** ist besser, da der Linker keinen Thunk generiert, wenn es nicht erforderlich ist. Thunks vergrößern Sie den Code (bei RISC-Systemen kann es mehrere Anweisungen sein) und kann die cacheleistung Ihres beeinträchtigen. Wenn Sie den Compiler, dass die Funktion in einer DLL ist aufzufordern, kann Sie einen indirekten Aufruf generieren.  
  
 Damit dieser Code:  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 Diese Anweisung generiert:  
  
```  
call DWORD PTR __imp_func1  
```  
  
 Es ist keine Thunk und keine `jmp` -Anweisung, damit der Code kleiner und weniger zeitaufwändig ist.  
  
 Andererseits, für die Funktionsaufrufe innerhalb einer DLL möchten nicht Sie einen indirekten Aufruf verwenden müssen. Sie wissen bereits, die Adresse einer Funktion. Da Zeit und Speicherplatz zum Laden und speichern Sie die Adresse der Funktion vor einem indirekten Aufruf erforderlich sind, ist ein direkter Aufruf immer schneller und kleinere. Sie verwenden möchten **von "__declspec(dllimport)" "** beim Aufrufen von DLL-Funktionen außerhalb der DLL selbst. Verwenden Sie keine **von "__declspec(dllimport)" "** in Funktionen innerhalb einer DLL, die beim Erstellen dieser DLL.  
  
## <a name="see-also"></a>Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)