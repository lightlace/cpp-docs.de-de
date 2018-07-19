---
title: Projektbuildfehler prj0009 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0009
dev_langs:
- C++
helpviewer_keywords:
- PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5692ec643f5e3fe1adebf68048a6c435ab05d6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318453"
---
# <a name="project-build-error-prj0009"></a>Projektbuildfehler PRJ0009
Erstellen Sie Protokoll konnte nicht zum Schreiben geöffnet werden.  
  
 **Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess geöffnet ist und nicht schreibgeschützt.**  
  
 Nach dem Festlegen der **Buildprotokollierung** Eigenschaft **Ja** und Durchführen einer Erstellung oder Neuerstellung, Visual C++ konnte das Buildprotokoll im exklusiven Modus öffnen.  
  
 Überprüfen der **Buildprotokollierung** öffnen, indem die **Optionen** (Dialogfeld) (auf der **Tools** Menü klicken Sie auf **Optionen** Befehl) und dann Auswählen von **VC++-Build** in der **Projekte** Ordner. Die Builddatei "BuildLog.htm" aufgerufen wird und die Zwischenverzeichnis $(intdir) geschrieben.  
  
 Mögliche Ursachen für diesen Fehler:  
  
-   Sie sind zwei Prozesse von Visual C++ und die gleiche Konfiguration des gleichen Projekts in beiden gleichzeitig erstellen möchten.  
  
-   Die Buildprotokolldatei aufgenommen wird in einem Prozess geöffnet, die die Datei sperrt.  
  
-   Der Benutzer nicht über die Berechtigung zum Erstellen einer Datei.  
  
-   Der aktuelle Benutzer besitzt nicht den Schreibzugriff auf die Datei "BuildLog.htm".