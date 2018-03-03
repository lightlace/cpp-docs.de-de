---
title: 'Ressourcencompiler: Schwerwiegender Fehler RW1022 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW1022
dev_langs:
- C++
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a78e54496b1b0db11d8b6d6f85b5142db0d4ad6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rw1022"></a>Ressourcencompiler: Schwerwiegender Fehler RW1022
**E/a-Fehler beim Schreiben der Datei**  
  
 Der Ressourcencompiler konnte nicht in eine Datei schreiben.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Es ist nicht genügend Speicherplatz verfügbar. Freier Speicherplatz muss über mindestens zwei Mal die Größe der ausführbaren Datei entsprechen, die Sie erstellen.  
  
2.  Das Volume ist schreibgeschützt.  
  
3.  Es liegt ein beschädigter Sektor vor.  
  
4.  Freigabeverletzung.