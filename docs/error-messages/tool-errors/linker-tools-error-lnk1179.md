---
title: Linkertoolfehler Lnk1179 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72a531397c3c101fbff937f293f772c5f6778523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300214"
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