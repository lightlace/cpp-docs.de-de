---
title: Befehlszeilenfehler D8027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc93edb939001a1e1bed5d3f7a4113e8483e81dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-error-d8027"></a>Befehlszeilenfehler D8027
"Komponente" kann nicht ausgeführt werden  
  
 Der Compiler konnte nicht ausgeführt, die Compilerkomponente von angegebenen oder den Linker.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Nicht genügend Arbeitsspeicher zum Laden der Komponente. Wenn NMAKE den Compiler, führen Sie den Compiler außerhalb der Makefile aufgerufen.  
  
2.  Das aktuelle Betriebssystem konnte die Komponente nicht ausgeführt werden. Vergewissern Sie sich der Pfad verweist auf die ausführbaren Dateien zu Ihrem Betriebssystem entsprechende.  
  
3.  Die Komponente wurde beschädigt. Kopieren Sie die Komponente aus der Verteilung Datenträger mithilfe der SETUP-Programm erneut.  
  
4.  Eine Option wurde falsch angegeben. Zum Beispiel:  
  
    ```  
    cl /B1 file1.c  
    ```