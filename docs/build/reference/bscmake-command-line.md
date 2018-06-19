---
title: BSCMAKE-Befehlszeile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7866d2960acdd89c3015470ef3971307ba162cd3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369496"
---
# <a name="bscmake-command-line"></a>BSCMAKE-Befehlszeile
Verwenden Sie die folgende Befehlszeilensyntax zum Ausführen von BSCMAKE:  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Optionen stehen nur in der `options` Feld in der Befehlszeile angegeben.  
  
 Die *Sbrfiles* Feld gibt einen oder mehrere .sbr-Dateien, die von einem Compiler oder Assembler erstellt. Trennen Sie die Namen der SBR-Dateien, durch Leerzeichen oder Tabstopps. Sie müssen die Erweiterung angeben. Es gibt keinen Standardwert. Geben Sie einen Pfad mit dem Dateinamen, und Sie können Betriebssystem-Platzhalter verwenden (* und?).  
  
 Bei einem inkrementellen Build können Sie neue .sbr-Dateien angeben, die nicht Teil des ursprünglichen Builds waren. Wenn Sie alle Beiträge in die Browserinformationsdatei bleiben möchten, müssen Sie alle SBR-Dateien (einschließlich abgeschnittene Dateien) angeben, die ursprünglich zum Erstellen der BSC-Datei verwendet wurden. Wenn Sie eine SBR-Datei nicht angeben, wird diese Datei Beitrag zum der Browserinformationsdatei entfernt.  
  
 Geben Sie eine verkürzten .sbr-Datei für einen vollständigen Build nicht. Eine vollständige Erstellung erfordert Beiträge aus allen angegebenen SBR-Dateien. Bevor Sie einen vollständigen Build durchzuführen, kompilieren Sie das Projekt, und erstellen Sie eine neue SBR-Datei für jede leere Datei.  
  
 Der folgende Befehl führt BSCMAKE zum Erstellen der Datei Main von drei SBR-Dateien:  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 Weitere Informationen finden Sie unter [BSCMAKE-Befehlsdatei](../../build/reference/bscmake-command-file-response-file.md) und [BSCMAKE-Optionen](../../build/reference/bscmake-options.md).  
  
## <a name="see-also"></a>Siehe auch  
 [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)