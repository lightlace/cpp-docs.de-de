---
title: Abschnitt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- section_CPP
- vc-pragma.section
dev_langs:
- C++
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10f5783c6712852bfb53f457cea174f699c01ea0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="section"></a>section
Erstellt einen Abschnitt in einer OBJ-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Bedeutung der Begriffe *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 Sobald ein Abschnitt definiert wurde, bleibt er für den Rest der Kompilierung gültig. Sie müssen allerdings verwenden [__declspec(allocate)](../cpp/allocate.md) oder nichts wird im Abschnitt platziert werden.  
  
 *Abschnittsname* ist ein erforderlicher Parameter, die den Namen des Abschnitts. Der Name darf keinem Standard-Abschnittsnamen ähneln. Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.  
  
 `attributes` ist ein optionaler Parameter, der aus einem oder mehreren durch Kommas getrennten Attributen besteht, die Sie dem Abschnitt zuweisen möchten. Mögliche `attributes`-Parameter sind:  
  
 **read**  
 Ermöglicht Lesevorgänge für Daten.  
  
 **write**  
 Ermöglicht Schreibvorgänge für Daten.  
  
 **execute**  
 Ermöglicht die Ausführung von Code.  
  
 **shared**  
 Gibt den Abschnitt für alle Prozesse frei, die das Image laden.  
  
 **nopage**  
 Markiert den Abschnitt als nicht auslagerbar; nützlich für Win32-Gerätetreiber.  
  
 **nocache**  
 Markiert den Abschnitt als nicht zwischenspeicherbar; nützlich für Win32-Gerätetreiber.  
  
 **discard**  
 Markiert den Abschnitt als entfernbar; nützlich für Win32-Gerätetreiber.  
  
 **remove**  
 Markiert den Abschnitt als nicht speicherresident; Virtuelle Gerätetreiber (V*x*D) nur.  
  
 Wenn Sie keine Attribute angeben, enthält der Abschnitt Lese- und Schreibattribute.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel identifiziert die erste Anweisung den Abschnitt und seine Attribute. Die Ganzzahl `j` wird nicht in `mysec` eingefügt, da sie nicht mit `__declspec(allocate)` deklariert wurde. `j` wird in den Datenbereich eingefügt. Die Ganzzahl `i` wird aufgrund ihres `mysec`-Speicherklassenattributs in `__declspec(allocate)` eingefügt.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)