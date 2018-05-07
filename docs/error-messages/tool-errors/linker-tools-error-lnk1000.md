---
title: Linkertoolfehler Lnk1000 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1000
dev_langs:
- C++
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f67df9c53b79fabfc9559380b5b57a72e64cb8a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1000"></a>Linkertoolfehler LNK1000
Unbekannter Fehler; Dokumentation für die Optionen für technischen support  
  
 Notieren Sie die Umstände des Fehlers, versuchen Sie, das Problem zu isolieren, und erstellen einen reproduzierbaren Testfall wenden Sie sich an `Microsoft Product Support Services`. Informationen zum Überprüfen und diese Fehler melden, finden Sie unter [ http://support.microsoft.com/default.aspx?scid=kb; En-us; 134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Dieser Fehler kann ausgegeben werden, wenn Sie die standardmäßigen Headerdateien (z. B. dos.h) und Ihre eigenen Dateien kombinieren. `#include` der Standardheader zuerst, dann eigene Headerdateien.