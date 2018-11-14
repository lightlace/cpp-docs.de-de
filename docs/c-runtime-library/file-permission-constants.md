---
title: Dateiberechtigungskonstanten
ms.date: 11/04/2016
f1_keywords:
- _S_IWRITE
- _S_IREAD
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: 0e4a60b5f3dad70f881387d5befca2def9bff7f3
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520425"
---
# <a name="file-permission-constants"></a>Dateiberechtigungskonstanten

## <a name="syntax"></a>Syntax

```

#include <sys/stat.h>
```

## <a name="remarks"></a>Hinweise

Eine der folgenden Konstanten ist erforderlich, wenn `_O_CREAT` (`_open`, `_sopen`) angegeben wird.

Das `pmode`-Argument gibt die Dateiberechtigungseinstellungen wie folgt an.

|Konstante|Bedeutung|
|--------------|-------------|
|`_S_IREAD`|Lesen erlaubt|
|`_S_IWRITE`|Schreiben erlaubt|
|`_S_IREAD` &#124; `_S_IWRITE`|Lesen und Schreiben erlaubt|

Bei Verwendung als `pmode`-Argument für `_umask` legt die Manifestkonstante die Berechtigungseinstellung wie folgt fest.

|Konstante|Bedeutung|
|--------------|-------------|
|`_S_IREAD`|Schreiben nicht erlaubt (Datei ist schreibgeschützt)|
|`_S_IWRITE`|Lesen nicht erlaubt (Datei ist lesegeschützt)|
|`_S_IREAD` &#124; `_S_IWRITE`|Weder Lesen noch Schreiben erlaubt|

## <a name="see-also"></a>Siehe auch

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[Standardtypen](../c-runtime-library/standard-types.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)