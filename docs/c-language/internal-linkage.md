---
title: Interne Verknüpfung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b5703ca23a30cdb1d080e1dc379dabfc6c0df1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383994"
---
# <a name="internal-linkage"></a>Interne Verknüpfung
Wenn die Deklaration eines Dateigültigkeitsbereichs-Bezeichners für ein Objekt oder eine Funktion den *Speicherklassenspezifizierer* **static** enthält, hat der Bezeichner eine interne Verknüpfung. Andernfalls hat der Bezeichner eine externe Bindung. Weitere Informationen erhalten Sie in der Erläuterung der *Speicherklassenspezifizierer*-Nichtterminale unter [Speicherklassen](../c-language/c-storage-classes.md).  
  
 Innerhalb einer Übersetzungseinheit kennzeichnet jede Instanz eines Bezeichners mit interner Bindung denselben Bezeichner bzw. dieselbe Funktion. Intern gebundene Bezeichner sind für eine Übersetzungseinheit eindeutig.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)