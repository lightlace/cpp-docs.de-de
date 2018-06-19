---
title: Projektbuildfehler PRJ0050 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0050
dev_langs:
- C++
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ad17614f693e313190dba9cc767c023981dec34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318512"
---
# <a name="project-build-error-prj0050"></a>Projektbuildfehler PRJ0050
Fehler beim Registrieren der Ausgabe. Stellen Sie sicher, dass Sie die entsprechenden Berechtigungen zum Ändern der Registrierung haben.  
  
 Das Buildsystem von Visual C++ konnte nicht aus, um die Ausgabe des Builds (Dll oder .exe) zu registrieren. Sie müssen als Administrator die Registrierung geändert angemeldet sein.  
  
 Wenn Sie eine DLL-Datei erstellen, können Sie versuchen, die DLL-Datei manuell mit regsvr32.exe registrieren, es können Informationen zu den Ursachen der Build wird angezeigt.  
  
 Wenn Sie eine DLL-Datei nicht erstellen, sehen Sie sich das Buildprotokoll für den Befehl, der einen Fehler verursacht hat.