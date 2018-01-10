---
title: BSCMAKE-Fehler BK1506 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1506
dev_langs: C++
helpviewer_keywords: BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f553646689fd1e703e10f100bca6d989c8f767d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE-Fehler BK1506
'Dateiname' kann nicht geöffnet werden [: Grund]  
  
 BSCMAKE kann die Datei nicht öffnen.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Datei von einem anderen Prozess gesperrt. Wenn `reason` sagt **Berechtigung verweigert**, der Browser kann mithilfe der Datei. Schließen Sie das Fenster durchsuchen, und wiederholen Sie den Build.  
  
2.  Ein voller Datenträger.  
  
3.  Ein Hardwarefehler.  
  
4.  Die angegebene Ausgabedatei hat den gleichen Namen wie ein vorhandenes Unterverzeichnis.