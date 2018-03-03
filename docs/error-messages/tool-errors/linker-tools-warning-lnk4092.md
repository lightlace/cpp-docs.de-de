---
title: Linkertoolwarnung Lnk4092 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a25954b8dc15863a290bd5a99119cc79a5585e16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4092"></a>Linkertoolwarnung LNK4092
der freigegebene schreibbare Abschnitt "Abschnitt" enthält umsetzungen; Abbild kann möglicherweise nicht ordnungsgemäß ausgeführt.  
  
 Der Linker gibt diese Warnung immer dann, wenn Sie einen freigegebenen Abschnitt, der Sie ein potenziell schwerwiegendes Problem hinweist.  
  
 Eine Möglichkeit, Daten zwischen mehreren Prozessen gemeinsam ist, markieren Sie einen Abschnitt als "freigegeben". Markieren von einem Abschnitt als freigegebener kann jedoch Probleme verursachen. Beispielsweise haben Sie eine DLL, die Deklarationen wie folgt in einem freigegebenen Datenabschnitt enthält:  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 Der Linker kann nicht aufgelöst werden `pvar` , da der Wert hängt davon ab, in dem die DLL in den Arbeitsspeicher geladen wird, so legt er einen Datensatz zur Verschiebung in der DLL. Beim Laden der DLL in den Speicher und die Adresse des `var` aufgelöst werden kann und `pvar` zugewiesen. Wenn ein anderer Prozess dieselbe DLL lädt jedoch nicht geladen werden gleichzeitig zu beheben, die Umsetzung für die Adresse des `var` wird für den zweiten Prozess und der Adressraum des ersten Prozesses an die falsche Adresse werden aktualisiert.