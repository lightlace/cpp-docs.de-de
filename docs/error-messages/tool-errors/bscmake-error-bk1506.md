---
title: BSCMAKE-Fehler BK1506 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e19ec77818c8017387519b03e400c09d47021bc5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE-Fehler BK1506
'Dateiname' kann nicht geöffnet werden [: Grund]  
  
 BSCMAKE kann die Datei nicht öffnen.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Datei von einem anderen Prozess gesperrt. Wenn `reason` sagt **Berechtigung verweigert**, der Browser kann mithilfe der Datei. Schließen Sie das Fenster durchsuchen, und wiederholen Sie den Build.  
  
2.  Ein voller Datenträger.  
  
3.  Ein Hardwarefehler.  
  
4.  Die angegebene Ausgabedatei hat den gleichen Namen wie ein vorhandenes Unterverzeichnis.