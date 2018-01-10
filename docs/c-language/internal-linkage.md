---
title: "Interne Verknüpfung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e6ca8a9e9804aa6c14077b023d0014062067f324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="internal-linkage"></a>Interne Verknüpfung
Wenn die Deklaration eines Dateigültigkeitsbereichs-Bezeichners für ein Objekt oder eine Funktion den *Speicherklassenspezifizierer* **static** enthält, hat der Bezeichner eine interne Verknüpfung. Andernfalls hat der Bezeichner eine externe Bindung. Weitere Informationen erhalten Sie in der Erläuterung der *Speicherklassenspezifizierer*-Nichtterminale unter [Speicherklassen](../c-language/c-storage-classes.md).  
  
 Innerhalb einer Übersetzungseinheit kennzeichnet jede Instanz eines Bezeichners mit interner Bindung denselben Bezeichner bzw. dieselbe Funktion. Intern gebundene Bezeichner sind für eine Übersetzungseinheit eindeutig.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)