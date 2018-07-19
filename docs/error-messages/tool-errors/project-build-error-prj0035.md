---
title: Projektbuildfehler prj0035 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0035
dev_langs:
- C++
helpviewer_keywords:
- PRJ0035
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52d4726cd6fc8091225532b2cfda33c6115c673a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321859"
---
# <a name="project-build-error-prj0035"></a>Projektbuildfehler PRJ0035
XML-Datei "File" enthält die Unicode-Inhalte, die nicht in ANSI-Codepage des Benutzers übersetzt werden konnte.  
  
 ***Unicode-Inhalt der Datei***  
  
 ***Datei*** ist die XML-Datei als die Befehlszeile für das Web Deploy-Tool erstellt.  
  
 Das Projektsystem hat Unicode-Zeichen in eine bestimmte Eigenschaft gefunden, auf der Seite der Web Deploy-Eigenschaft, die ordnungsgemäß für ANSI übersetzt werden kann.  
  
 Die Auflösung für diesen Fehler besteht darin, aktualisieren den Inhalt der Eigenschaft für die von ANSI verwenden oder die Codepage auf dem Computer installieren und als dem als Standard festgelegt.