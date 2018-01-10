---
title: Projektbuildfehler PRJ0050 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0050
dev_langs: C++
helpviewer_keywords: PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9d9b123da2e32db0f695c31bc9643a481d352b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0050"></a>Projektbuildfehler PRJ0050
Fehler beim Registrieren der Ausgabe. Stellen Sie sicher, dass Sie die entsprechenden Berechtigungen zum Ändern der Registrierung haben.  
  
 Das Buildsystem von Visual C++ konnte nicht aus, um die Ausgabe des Builds (Dll oder .exe) zu registrieren. Sie müssen als Administrator die Registrierung geändert angemeldet sein.  
  
 Wenn Sie eine DLL-Datei erstellen, können Sie versuchen, die DLL-Datei manuell mit regsvr32.exe registrieren, es können Informationen zu den Ursachen der Build wird angezeigt.  
  
 Wenn Sie eine DLL-Datei nicht erstellen, sehen Sie sich das Buildprotokoll für den Befehl, der einen Fehler verursacht hat.