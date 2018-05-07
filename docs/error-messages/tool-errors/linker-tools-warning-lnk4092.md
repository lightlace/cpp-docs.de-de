---
title: Linkertoolwarnung Lnk4092 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72edd9e75dbc781355396e38f767a64c1ded3aa9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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