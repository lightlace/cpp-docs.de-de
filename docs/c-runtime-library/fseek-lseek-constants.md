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
ms.openlocfilehash: 67599ced3ee775d9e6d702a9fb9e66e0580240e4
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519151"
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