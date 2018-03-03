---
title: "Keine Verknüpfung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: abacc6fbd49f9f42620385a4206c9412648c173b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="no-linkage"></a>Keine Verknüpfung
Wenn eine Deklaration für einen Bezeichner in einem Block den `extern`-Speicherklassenspezifizierer nicht enthält, hat der Bezeichner keine Bindung und ist für die Funktion eindeutig.  
  
 Die folgenden Bezeichner haben keine Verknüpfung:  
  
-   Ein Bezeichner, der als etwas anderes als ein Objekt oder eine Funktion deklariert wurde  
  
-   Ein Bezeichner, der zum Funktionsparameter deklariert wurde  
  
-   Ein Blockbereichsbezeichner für ein Objekt, das ohne den `extern`-Speicherklassenspezifizierer deklariert wurde  
  
 Wenn ein Bezeichner keine Verknüpfung aufweist, wird durch erneutes Deklarieren des gleichen Namens (in einem Deklarator oder Typspezifizierer) auf der gleichen Gültigkeitsebene einen Fehler bei der Symbolneudefinition.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)