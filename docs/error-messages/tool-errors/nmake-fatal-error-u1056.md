---
title: 'NMAKE: Schwerwiegender Fehler U1056 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1056
dev_langs:
- C++
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19890e290c98fd9602d755ad35f9d47204bd6c24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE: Schwerwiegender Fehler U1056
Befehlsprozessors wurde nicht gefunden.  
  
 Befehlsprozessors wies nicht den im angegebenen Pfad die **COMSPEC** oder **Pfad** Umgebungsvariablen.  
  
 NMAKE verwendet COMMAND.COM oder cmd ein. EXE-Datei als ein Befehlsprozessors, wenn Sie Befehle ausführen. Es sucht Befehlsprozessors zuerst in den Pfad festlegen, die **COMSPEC**. Wenn **COMSPEC** ist nicht vorhanden, NMAKE sucht die Verzeichnisse im angegebenen **Pfad**.