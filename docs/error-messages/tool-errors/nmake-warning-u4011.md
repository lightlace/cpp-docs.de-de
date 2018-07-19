---
title: 'NMAKE: Warnung U4011 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U4011
dev_langs:
- C++
helpviewer_keywords:
- U4011
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af9c0f90c507eebe212a9c3cbfb2f2d21cded43d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320794"
---
# <a name="nmake-warning-u4011"></a>NMAKE: Warnung U4011
'Target': nicht alle abhängigen Elemente verfügbar. Ziel nicht erstellt  
  
 Ein Nachfolger des angegebenen Ziels ist nicht vorhanden oder wurde nicht aktualisiert, und ein Befehl zur Aktualisierung der abhängigen zurückgegeben einen Exitcode. Die Option/k mitgeteilt NMAKE nicht verbundene Teile des Builds Verarbeitung fortzusetzen, und stellen einen Exitcode 1 aus, wenn die NMAKE-Sitzung abgeschlossen ist.  
  
 Diese Warnung wird für die Warnung vorangestellt [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) für jede abhängige Datei, die nicht erstellt oder aktualisiert werden konnten.