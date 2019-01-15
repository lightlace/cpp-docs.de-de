---
title: fseek- und _lseek-Konstanten
ms.date: 11/04/2016
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
ms.openlocfilehash: a97495aaa5ab0a79ed71a48a12162bd14fc60131
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220451"
---
# <a name="fseek-lseek-constants"></a>fseek- und _lseek-Konstanten

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Hinweise

Das *origin*-Argument gibt die Ausgangsposition an und kann eine der folgenden Manifestkonstanten sein:

|Konstante|Bedeutung|
|--------------|-------------|
|`SEEK_END`|Ende der Datei|
|`SEEK_CUR`|Aktuelle Position des Dateizeigers|
|`SEEK_SET`|Anfang der Datei|

## <a name="see-also"></a>Siehe auch

[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)
