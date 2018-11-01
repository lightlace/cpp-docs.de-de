---
title: Befehlszeilenwarnung D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 3fd8d442dfabaf2f03d8b564c9fdfb1537f6ff28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599432"
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