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
ms.openlocfilehash: 0e042cddce6edf079aa54f114130f9750412e327
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742708"
---
# <a name="file-permission-constants"></a>Dateiberechtigungskonstanten

## <a name="syntax"></a>Syntax

```
#include <sys/stat.h>
```

## <a name="remarks"></a>Anmerkungen

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
