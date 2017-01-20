---
title: "Linkertoolwarnung LNK4006"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4006"
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Symbol bereits in Objekt definiert; zweite Definition wird ignoriert  
  
 Das angegebene *Symbol*, das in seiner ergänzten Form dargestellt wird, wurde mehrfach definiert.  Wenn diese Warnung auftritt, wird *Symbol* zweimal hinzugefügt, es wird jedoch nur seine erste Form verwendet.  
  
 Diese Warnung kann ausgegeben werden, wenn Sie versuchen, zwei Importbibliotheken in einer zusammenzuführen.  
  
 Wenn Sie die C\-Laufzeitbibliothek neu erstellen, können Sie diese Meldung ignorieren.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Das angegebene *Symbol* ist möglicherweise eine Paketfunktion, die durch die Kompilierung mit [\/Gy](../../build/reference/gy-enable-function-level-linking.md) erstellt wurde.  Dieses Symbol wurde in mehr als eine Datei eingelesen, zwischen den Kompilierungen jedoch geändert.  Kompilieren Sie alle Dateien neu, die das *Symbol* enthalten.  
  
2.  Das angegebene *Symbol* kann in zwei Memberobjekten in verschiedenen Bibliotheken unterschiedlich definiert sein.  
  
3.  Ein absolutes Symbol wurde möglicherweise zweimal mit unterschiedlichen Werten in zwei Definitionen definiert.  
  
4.  Tritt die Fehlermeldung beim Kombinieren von Bibliotheken auf, ist das *Symbol* bereits in der Bibliothek, der es hinzugefügt wird, vorhanden.