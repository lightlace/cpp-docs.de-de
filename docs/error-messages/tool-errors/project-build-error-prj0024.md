---
title: Projektbuildfehler prj0024 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0024
dev_langs: C++
helpviewer_keywords: PRJ0024
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cf9ad974856f132599932a32b954e50453adf56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0024"></a>Projektbuildfehler PRJ0024
Unicode-' Pfad ' konnte nicht in ANSI-Codepage des Benutzers übersetzt werden.  
  
 ***Pfad*** wird die ursprüngliche Unicodeversion der Pfadzeichenfolge. Dieser Fehler kann auftreten, in Fällen, in dem es ist ein Unicodepfad, der für die aktuelle Codepage des Systems nicht direkt in ANSI übersetzt werden kann.  
  
 Dieser Fehler kann auftreten, wenn Sie arbeiten mit einem Projekt, das entwickelt wurde auf einem System mit einer Codepage, die nicht auf Ihrem Computer ist.  
  
 Die Auflösung für diesen Fehler ist, aktualisieren Sie den Pfad, um die ANSI-Text verwenden oder um die Codepage auf dem Computer installieren und als dem als Standard festgelegt.