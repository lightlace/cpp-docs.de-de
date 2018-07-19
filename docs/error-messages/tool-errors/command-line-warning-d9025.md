---
title: Befehlszeilenwarnung D9025 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9025
dev_langs:
- C++
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3875a2cbd065fd5ad887267bcc80748fa9845d0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298849"
---
# <a name="command-line-warning-d9025"></a>Befehlszeilenwarnung D9025
Überschreiben von 'option1' mit 'option2'  
  
 Die *option1* -Option wurde angegeben, aber durch überschrieben *option2*. Die *option2* Option wurde verwendet.  
  
 Wenn zwei Optionen widersprüchliche oder inkompatible Direktiven angeben, wird die Richtlinie angegeben oder impliziert die Option am weitesten rechts in der Befehlszeile verwendet.  
  
 Wenn Sie diese Warnung beim Kompilieren von der Entwicklungsumgebung erhalten und sich nicht sicher sind, in dem die in Konflikt stehenden Optionen von kommen, berücksichtigen Sie Folgendes:  
  
-   Eine Option kann im Code oder in den projekteinstellungen für das Projekt angegeben werden. Bei Betrachtung des Compilers [Befehlszeile Eigenschaftenseiten](../../ide/command-line-property-pages.md) und wenn Sie die in Konflikt stehenden Optionen finden Sie unter der **alle Optionen** Feld, und klicken Sie dann die Optionen in den Eigenschaftenseiten des Projekts, andernfalls die Optionen festgelegt werden werden im Quellcode festgelegt.  
  
     Wenn die Optionen in den Eigenschaftenseiten des Projekts festgelegt werden, suchen Sie auf der Compiler Präprozessor Eigenschaftenseite (mit den Projektknoten im Projektmappen-Explorer ausgewählt).  Wenn Sie nicht die Option dort festlegen, stellen Sie sicher, die seiteneinstellungen Präprozessor-Eigenschaft für jede Quelle-Codedatei (in Projektmappen-Explorer) angezeigt wird er es nicht hinzugefügt.  
  
     Wenn die Optionen im Code festgelegt sind, konnte es entweder im Code oder in der Windows-Header festgelegt werden.  Sie könnten versuchen, eine vorverarbeitete Datei erstellen ([/p](../../build/reference/p-preprocess-to-a-file.md)) und das Symbol gesucht.