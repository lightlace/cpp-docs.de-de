---
title: Projektbuildfehler prj0032 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0032
dev_langs: C++
helpviewer_keywords: PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3ea007346793f8d06ac85f20649b7d348014e17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0032"></a>Projektbuildfehler PRJ0032
Die Outputs-Eigenschaft für den benutzerdefinierten Buildschritt auf Projektebene enthaltenen "Makros", die als "Macro_expansion" ausgewertet wird.  
  
 Ein benutzerdefinierten Buildschritt an einem Projekt musste fehlerhafte Ausgabe wahrscheinliche Ursache: ein Makro Auswertung Problem. Dieser Fehler kann auch dies bedeuten, dass der Pfad weist ein ungültiges Format ist, enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.