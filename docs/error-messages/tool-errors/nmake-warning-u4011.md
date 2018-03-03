---
title: 'NMAKE: Warnung U4011 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ae15a3912fe3172e9dec98e1a90a3a262c47117
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4011"></a>NMAKE: Warnung U4011
'Target': nicht alle abhängigen Elemente verfügbar. Ziel nicht erstellt  
  
 Ein Nachfolger des angegebenen Ziels ist nicht vorhanden oder wurde nicht aktualisiert, und ein Befehl zur Aktualisierung der abhängigen zurückgegeben einen Exitcode. Die Option/k mitgeteilt NMAKE nicht verbundene Teile des Builds Verarbeitung fortzusetzen, und stellen einen Exitcode 1 aus, wenn die NMAKE-Sitzung abgeschlossen ist.  
  
 Diese Warnung wird für die Warnung vorangestellt [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) für jede abhängige Datei, die nicht erstellt oder aktualisiert werden konnten.