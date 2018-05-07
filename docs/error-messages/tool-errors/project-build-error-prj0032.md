---
title: Projektbuildfehler prj0032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0032
dev_langs:
- C++
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6be9a343ae9d9ce1e3d862cc0a397f1d61ccdea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0032"></a>Projektbuildfehler PRJ0032
Die Outputs-Eigenschaft für den benutzerdefinierten Buildschritt auf Projektebene enthaltenen "Makros", die als "Macro_expansion" ausgewertet wird.  
  
 Ein benutzerdefinierten Buildschritt an einem Projekt musste fehlerhafte Ausgabe wahrscheinliche Ursache: ein Makro Auswertung Problem. Dieser Fehler kann auch dies bedeuten, dass der Pfad weist ein ungültiges Format ist, enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.