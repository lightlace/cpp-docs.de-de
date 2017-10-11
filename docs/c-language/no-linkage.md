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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 278325c1ad1b31ce20b6a17034be5e4731f6da78
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
