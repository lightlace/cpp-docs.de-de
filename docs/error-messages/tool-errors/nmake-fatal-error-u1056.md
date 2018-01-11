---
title: 'NMAKE: Schwerwiegender Fehler U1056 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1056
dev_langs: C++
helpviewer_keywords: U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 41db646e2559051c11de5265900dde8ad0a03214
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE: Schwerwiegender Fehler U1056
Befehlsprozessors wurde nicht gefunden.  
  
 Befehlsprozessors wies nicht den im angegebenen Pfad die **COMSPEC** oder **Pfad** Umgebungsvariablen.  
  
 NMAKE verwendet COMMAND.COM oder cmd ein. EXE-Datei als ein Befehlsprozessors, wenn Sie Befehle ausführen. Es sucht Befehlsprozessors zuerst in den Pfad festlegen, die **COMSPEC**. Wenn **COMSPEC** ist nicht vorhanden, NMAKE sucht die Verzeichnisse im angegebenen **Pfad**.