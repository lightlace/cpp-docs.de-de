---
title: Befehlszeilenwarnung D9025 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D9025
dev_langs:
- C++
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d95c4c16b472f0e1b37a981df7f73ff573d06447
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-warning-d9025"></a>Befehlszeilenwarnung D9025
Überschreiben von 'option1' mit 'option2'  
  
 Die *option1* -Option wurde angegeben, aber durch überschrieben *option2*. Die *option2* Option wurde verwendet.  
  
 Wenn zwei Optionen widersprüchliche oder inkompatible Direktiven angeben, wird die Richtlinie angegeben oder impliziert die Option am weitesten rechts in der Befehlszeile verwendet.  
  
 Wenn Sie diese Warnung beim Kompilieren von der Entwicklungsumgebung erhalten und sich nicht sicher sind, in dem die in Konflikt stehenden Optionen von kommen, berücksichtigen Sie Folgendes:  
  
-   Eine Option kann im Code oder in den projekteinstellungen für das Projekt angegeben werden. Bei Betrachtung des Compilers [Befehlszeile Eigenschaftenseiten](../../ide/command-line-property-pages.md) und wenn Sie die in Konflikt stehenden Optionen finden Sie unter der **alle Optionen** Feld, und klicken Sie dann die Optionen in den Eigenschaftenseiten des Projekts, andernfalls die Optionen festgelegt werden werden im Quellcode festgelegt.  
  
     Wenn die Optionen in den Eigenschaftenseiten des Projekts festgelegt werden, suchen Sie auf der Compiler Präprozessor Eigenschaftenseite (mit den Projektknoten im Projektmappen-Explorer ausgewählt).  Wenn Sie nicht die Option dort festlegen, stellen Sie sicher, die seiteneinstellungen Präprozessor-Eigenschaft für jede Quelle-Codedatei (in Projektmappen-Explorer) angezeigt wird er es nicht hinzugefügt.  
  
     Wenn die Optionen im Code festgelegt sind, konnte es entweder im Code oder in der Windows-Header festgelegt werden.  Sie könnten versuchen, eine vorverarbeitete Datei erstellen ([/p](../../build/reference/p-preprocess-to-a-file.md)) und das Symbol gesucht.