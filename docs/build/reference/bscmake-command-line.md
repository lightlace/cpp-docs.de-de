---
title: BSCMAKE-Befehlszeile | Microsoft-Dokumentation
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
ms.openlocfilehash: b79f7e7c181112877c795f3601e8211e70403563
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207746"
---
# <a name="bscmake-command-line"></a>BSCMAKE-Befehlszeile
Verwenden Sie die folgende Befehlszeilensyntax, führen Sie BSCMAKE:  
  
```  
BSCMAKE [options] sbrfiles  
```  
  
 Optionen stehen nur in der `options` Feld in der Befehlszeile.  
  
 Die *Sbrfiles* Feld gibt einen oder mehrere .sbr-Dateien, die von einem Compiler oder den Assembler erstellt. Trennen Sie die Namen der SBR-Dateien mit Leerzeichen oder Tabstopps. Sie müssen die Erweiterung angeben. Es gibt keinen Standardwert. Sie können einen Pfad angeben, mit dem Dateinamen, und können Sie Betriebssystem-Platzhalter verwenden (\* und?).  
  
 Bei einem inkrementellen Build können Sie neue .sbr-Dateien angeben, die nicht Teil des ursprünglichen Builds waren. Wenn Sie alle Beiträge in die Browserinformationsdatei bleiben möchten, müssen Sie alle .sbr-Dateien (einschließlich abgeschnittene Dateien) angeben, die ursprünglich zum Erstellen der BSC-Datei verwendet wurden. Wenn Sie eine SBR-Datei weglassen, wird diese Datei Beitrag auf der Browserinformationsdatei entfernt.  
  
 Geben Sie eine verkürzten .sbr-Datei für einen vollständigen Build nicht. Ein vollständiger Build muss es sich um Beiträge aus allen angegebenen SBR-Dateien. Bevor Sie einen vollständigen Build durchzuführen, kompilieren Sie das Projekt erneut, und erstellen Sie eine neue .sbr-Datei für jede Datei leer.  
  
 Der folgende Befehl führt BSCMAKE zum Erstellen der Datei Main von drei SBR-Dateien:  
  
```  
BSCMAKE main.sbr file1.sbr file2.sbr  
```  
  
 Weitere Informationen finden Sie unter [BSCMAKE-Befehlsdatei](../../build/reference/bscmake-command-file-response-file.md) und [BSCMAKE-Optionen](../../build/reference/bscmake-options.md).  
  
## <a name="see-also"></a>Siehe auch  
 [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)