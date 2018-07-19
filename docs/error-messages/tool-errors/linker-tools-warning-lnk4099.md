---
title: Linkertoolwarnung Lnk4099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22764705b35b2e882c5a03e819c9812d084dc118
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300812"
---
# <a name="linker-tools-warning-lnk4099"></a>Linkertoolwarnung LNK4099
PDB-Datei "Dateiname" wurde nicht mit "Objektbibliothek" oder auf "%Path;" gefunden. Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären  
  
 Der Linker konnte die PDB-Datei zu suchen. Kopieren Sie ihn in das Verzeichnis mit `object/library`.  
  
 So suchen Sie den Namen der PDB-Datei der Objektdatei zugeordnet:  
  
1.  Extrahieren Sie eine Objektdatei aus der Bibliothek mit [Lib](../../build/reference/lib-reference.md) **/extrahieren:**`objectname`**obj** `xyz` **lib**.  
  
2.  Überprüfen Sie den Pfad zur PDB-Datei mit **Dumpbin/section:.Debug$ T/RAWDATA** `objectname` **obj**.  
  
 Sie könnten auch Kompilieren mit ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md), sodass die PDB-Datei muss nicht verwendet werden, oder entfernen Sie die [/DEBUG](../../build/reference/debug-generate-debug-info.md) (Linkeroption), wenn Sie PDB-Dateien für die Objekte keine verknüpfen.