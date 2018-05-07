---
title: Projektbuildfehler prj0024 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0024
dev_langs:
- C++
helpviewer_keywords:
- PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59bf76aba80093bf9e8e653bdfb9fad49687a501
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0024"></a>Projektbuildfehler PRJ0024
Unicode-' Pfad ' konnte nicht in ANSI-Codepage des Benutzers übersetzt werden.  
  
 ***Pfad*** wird die ursprüngliche Unicodeversion der Pfadzeichenfolge. Dieser Fehler kann auftreten, in Fällen, in dem es ist ein Unicodepfad, der für die aktuelle Codepage des Systems nicht direkt in ANSI übersetzt werden kann.  
  
 Dieser Fehler kann auftreten, wenn Sie arbeiten mit einem Projekt, das entwickelt wurde auf einem System mit einer Codepage, die nicht auf Ihrem Computer ist.  
  
 Die Auflösung für diesen Fehler ist, aktualisieren Sie den Pfad, um die ANSI-Text verwenden oder um die Codepage auf dem Computer installieren und als dem als Standard festgelegt.