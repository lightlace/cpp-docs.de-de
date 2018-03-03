---
title: Projektbuildfehler prj0031 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0031
dev_langs:
- C++
helpviewer_keywords:
- PRJ0031
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f1c07145f42e1ad71fb6c2a3542d9014b7e33b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0031"></a>Projektbuildfehler PRJ0031
Die Outputs-Eigenschaft für den benutzerdefinierten Build Schritt "Macro_expansion" für die Datei "File" enthalten "Makro" das ausgewertet wird.  
  
 Ein benutzerdefinierten Buildschritt für eine Datei mussten fehlerhafte Ausgabe wahrscheinliche Ursache: ein Makro Auswertung Problem. Dieser Fehler kann auch dies bedeuten, dass der Pfad weist ein ungültiges Format ist, enthält Zeichen oder eine Kombination von Zeichen, die in einem Dateipfad unzulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe. Der ausgewertete Pfad ist ein absoluter Pfad vom Projektverzeichnis.