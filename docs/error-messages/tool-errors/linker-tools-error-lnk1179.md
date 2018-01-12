---
title: Linkertoolfehler Lnk1179 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1179
dev_langs: C++
helpviewer_keywords: LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93b042e928331e369d64a45aa27f5f613ce9fc31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1179"></a>Linkertoolfehler LNK1179
Ungültige oder beschädigte Datei: Doppelte COMDAT "Dateiname"  
  
 Ein Objektmodul enthält zwei oder mehr COMDATs mit dem gleichen Namen.  
  
 Dieser Fehler kann verursacht werden, mithilfe von [/h](../../build/reference/h-restrict-length-of-external-names.md), was begrenzt die Länge externer Namen und [/Gy](../../build/reference/gy-enable-function-level-linking.md), die Funktionen in COMDATs gepackt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code `function1` und `function2` in den ersten acht Zeichen identisch sind. Beim Kompilieren mit **/Gy** und **/H8** entsteht ein Bindungsfehler.  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```