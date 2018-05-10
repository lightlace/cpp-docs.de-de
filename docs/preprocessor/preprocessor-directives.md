---
title: Präprozessordirektiven | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b73f6ce579f94d38621820a63888dc0aa5a75863
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="preprocessor-directives"></a>Präprozessoranweisungen
Präprozessordirektiven, wie z. B. `#define` und **#ifdef**, dienen im Allgemeinen, einfach zu ändern und Kompilieren in unterschiedlichen ausführungsumgebungen zu vereinfachen. Anweisungen in der Quelldatei weisen den Präprozessor an, bestimmte Aktionen auszuführen. Beispielsweise kann der Präprozessor Token im Text ersetzen, den Inhalt von anderen Dateien in die Quelldatei einfügen oder die Kompilierung eines Teils der Datei unterdrücken, indem er Textabschnitte entfernt. Präprozessorzeilen werden vor der Makroerweiterung erkannt und ausgeführt. Wenn also die Erweiterung eines Makros aussieht wie ein Präprozessorbefehl, wird dieser Befehl nicht vom Präprozessor erkannt.  
  
 Präprozessoranweisungen verwenden den gleichen Zeichensatz wie Quelldateianweisungen, mit der Ausnahme, dass Escapesequenzen nicht unterstützt werden. Der Zeichensatz, der in präprozessoranweisungen verwendet ist identisch mit der [ausführungszeichensatz](http://msdn.microsoft.com/en-us/a7901c61-524d-47c6-beb6-d9dacc2e72ed). Der Präprozessor erkennt auch negative Zeichenwerte.  
  
 Der Präprozessor erkennt die folgenden Anweisungen:  
  
|||||  
|-|-|-|-|  
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|  
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|  
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|  
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||  
  
 Das Nummernzeichen (**#**) müssen werden die ersten Leerstelle in der Zeile, die die Direktive an; enthält können Leerzeichen zwischen dem Nummernzeichen und dem ersten Buchstaben der Direktive angezeigt werden. Manche Direktiven enthalten Argumente oder Werte. Jeglichem Text, der eine Direktive folgt (außer einem Argument oder einem Wert, der Teil der Direktive ist) muss das einzeilige Kommentartrennzeichen vorangestellt werden (**//**) oder in Kommentartrennzeichen eingeschlossen ( **/ \* \*/**). Zeilen, die Präprozessordirektiven fortgesetzt werden können, durch die End-of-Line-Marker mit einem umgekehrten Schrägstrich unmittelbar vorausgeht (**\\**).  
  
 Präprozessoranweisungen können an beliebiger Stelle in einer Quelldatei auftreten, aber sie gelten nur für den Rest der Quelldatei.  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessor-Operatoren](../preprocessor/preprocessor-operators.md)   
 [Vordefinierte Makros](../preprocessor/predefined-macros.md)   
 [C/C++-Präprozessorreferenz](../preprocessor/c-cpp-preprocessor-reference.md)