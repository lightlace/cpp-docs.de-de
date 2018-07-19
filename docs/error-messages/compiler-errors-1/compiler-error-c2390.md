---
title: Compilerfehler C2390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a32a9ca77ba43e5f2866baed91b99103224dbc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198715"
---
# <a name="compiler-error-c2390"></a>Compilerfehler C2390
'Bezeichner': falsches Speicherklasse "Spezifizierer"  
  
 Die Speicherklasse gilt nicht für den globalen Gültigkeitsbereich-Bezeichner. Die Standardspeicherklasse wird anstelle der ungültige Klasse verwendet.  
  
 Folgende Lösungen möglich:  
  
-   Wenn der Bezeichner eine Funktion ist, deklarieren Sie es mit `extern` Speicher.  
  
-   Wenn der Bezeichner ein formaler Parameter oder eine lokale Variable ist, deklarieren Sie es mit dem automatisch Speicher.  
  
-   Wenn der Bezeichner eine globale Variable ist, deklarieren Sie ihn mit keine Speicherklasse (Auto-Speicher) ein.  
  
## <a name="example"></a>Beispiel  
  
-   Im folgende Beispiel wird C2390 generiert:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```