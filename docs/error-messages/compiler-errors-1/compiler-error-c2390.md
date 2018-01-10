---
title: Compilerfehler C2390 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2390
dev_langs: C++
helpviewer_keywords: C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93d4cbd9de274d53fdc0369c2b85dbf2e97af48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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