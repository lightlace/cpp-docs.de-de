---
title: Projektbuildfehler prj0036 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0036
dev_langs:
- C++
helpviewer_keywords:
- PRJ0036
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55ca9c282cbf36111bbc6b5d4316745508ccbb0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0036"></a>Projektbuildfehler PRJ0036
Die 'Zusätzliche Dateien'-Eigenschaft für das Webbereitstellungstool enthielt einen ungültigen Eintrag.  
  
 Die zusätzlichen Dateien-Eigenschaft auf der Eigenschaftenseite für die Webbereitstellung enthalten Fehler, mögliche Ursachen sind ein Makro Auswertung Problem. Dieser Fehler kann auch dies bedeuten, dass der Pfad weist ein ungültiges Format ist, enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.  
  
 Dieser Fehler kann auch dies bedeuten, dass eine der Dateien, die nicht vorhanden ist.