---
title: Projektbuildfehler prj0035 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0035
dev_langs:
- C++
helpviewer_keywords:
- PRJ0035
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b80fa6c7068d46ceed13b357c68cf30179ff0469
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0035"></a>Projektbuildfehler PRJ0035
XML-Datei "File" enthält die Unicode-Inhalte, die nicht in ANSI-Codepage des Benutzers übersetzt werden konnte.  
  
 ***Unicode-Inhalt der Datei***  
  
 ***Datei*** ist die XML-Datei als die Befehlszeile für das Web Deploy-Tool erstellt.  
  
 Das Projektsystem hat Unicode-Zeichen in eine bestimmte Eigenschaft gefunden, auf der Seite der Web Deploy-Eigenschaft, die ordnungsgemäß für ANSI übersetzt werden kann.  
  
 Die Auflösung für diesen Fehler besteht darin, aktualisieren den Inhalt der Eigenschaft für die von ANSI verwenden oder die Codepage auf dem Computer installieren und als dem als Standard festgelegt.