---
title: Projektbuildfehler prj0009 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0009
dev_langs: C++
helpviewer_keywords: PRJ0009
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ee183c24cf330b54a335efbd0bbe2b00e18d209
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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