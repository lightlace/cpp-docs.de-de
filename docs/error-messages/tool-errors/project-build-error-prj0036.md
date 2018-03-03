---
title: Projektbuildfehler prj0036 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0036
dev_langs:
- C++
helpviewer_keywords:
- PRJ0036
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 590c6cb8b69e7c6af4589e74817aa69f25737a11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0036"></a>Projektbuildfehler PRJ0036
Die 'Zusätzliche Dateien'-Eigenschaft für das Webbereitstellungstool enthielt einen ungültigen Eintrag.  
  
 Die zusätzlichen Dateien-Eigenschaft auf der Eigenschaftenseite für die Webbereitstellung enthalten Fehler, mögliche Ursachen sind ein Makro Auswertung Problem. Dieser Fehler kann auch dies bedeuten, dass der Pfad weist ein ungültiges Format ist, enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.  
  
 Dieser Fehler kann auch dies bedeuten, dass eine der Dateien, die nicht vorhanden ist.