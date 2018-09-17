---
title: STUB | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 151d7b425a7f397a05e3a06e9d94489a0c76f899
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725113"
---
# <a name="stub"></a>STUB

Wenn eine Moduldefinitionsdatei verwendet, die einen virtuellen Gerätetreiber (VxD) erstellt, können Sie einen Dateinamen angeben, der eine Anweisung-Struktur (definiert in WINNT. enthält H), die im virtuellen Gerätetreiber (VxD), statt der Standardheader verwendet werden.

```
STUB:filename
```

## <a name="remarks"></a>Hinweise

Eine entsprechende Möglichkeit zum angeben *Filename* ist mit der [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) -Linkeroption.

STUB gilt in eine Moduldefinitionsdatei, nur, wenn Sie einen VxD zu erstellen.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)