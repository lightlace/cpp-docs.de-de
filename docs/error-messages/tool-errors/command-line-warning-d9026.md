---
title: Befehlszeilenwarnung D9026 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07be633e56dad6c8f0b304a3c88c1b9919221d4a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079153"
---
# <a name="command-line-warning-d9026"></a>Befehlszeilenwarnung D9026

Optionen gelten für gesamte Befehlszeile.

Nachdem ein Dateiname angegeben wurde, wurde eine Option für einen Befehl angegeben. Die Option wurde in die Datei angewendet, die es vorangestellt.

Z. B. in den Befehl

```
CL verdi.c /G5 puccini.c
```

die Datei VERDI.c wird mit der Option/G5 und nicht vom Standard/G4 kompiliert werden.

Dieses Verhalten unterscheidet sich von der einigen früheren Versionen, die angewendet werden, nur die Optionen, die vor dem Dateinamen, wodurch VERDI.c angegeben kompiliert wird, mithilfe von/G4 und wurden mit/G5 kompiliert wird.