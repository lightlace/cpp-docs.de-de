---
title: 'Ressourcencompiler: Schwerwiegender Fehler RW1022 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1022
dev_langs:
- C++
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f57bb435d17cf1d539d558b5dead9c299f83494a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319181"
---
# <a name="resource-compiler-fatal-error-rw1022"></a>Ressourcencompiler: Schwerwiegender Fehler RW1022
**E/a-Fehler beim Schreiben der Datei**  
  
 Der Ressourcencompiler konnte nicht in eine Datei schreiben.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es ist nicht genügend Speicherplatz verfügbar. Freier Speicherplatz muss über mindestens zwei Mal die Größe der ausführbaren Datei entsprechen, die Sie erstellen.  
  
2.  Das Volume ist schreibgeschützt.  
  
3.  Es liegt ein beschädigter Sektor vor.  
  
4.  Freigabeverletzung.