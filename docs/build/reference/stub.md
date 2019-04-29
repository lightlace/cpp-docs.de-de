---
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 5224fdaa2a03dc615c9e7e7bb7f7ba822a40807e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318120"
---
# <a name="stub"></a>STUB

Wenn eine Moduldefinitionsdatei verwendet, die einen virtuellen Gerätetreiber (VxD) erstellt, können Sie einen Dateinamen angeben, der eine Anweisung-Struktur (definiert in WINNT. enthält H), die im virtuellen Gerätetreiber (VxD), statt der Standardheader verwendet werden.

```
STUB:filename
```

## <a name="remarks"></a>Hinweise

Eine entsprechende Möglichkeit zum angeben *Filename* ist mit der [/STUB](stub-ms-dos-stub-file-name.md) -Linkeroption.

STUB gilt in eine Moduldefinitionsdatei, nur, wenn Sie einen VxD zu erstellen.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](rules-for-module-definition-statements.md)
