---
title: /ERRORREPORT (editbin.exe)
description: Referenz für die Befehlszeilenoption "Microsoft EDITBIN Utility/errorreport".
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
helpviewer_keywords:
- -ERRORREPORT editbin option
- ERRORREPORT editbin option
- /ERRORREPORT editbin option
ms.assetid: eca66ac3-b754-4bd7-9dd4-e04fc79a71b6
ms.openlocfilehash: 6c2ec8b6cda7b794114ed38cfb72b885bf2e38a1
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257591"
---
# <a name="errorreport-editbinexe"></a>/ERRORREPORT (editbin.exe)

> [!NOTE]
> Die/errorreport-Option ist veraltet. Ab Windows Vista wird die Fehlerberichterstattung durch [Windows-Fehlerberichterstattung (wer)](/windows/win32/wer/windows-error-reporting) -Einstellungen gesteuert.

## <a name="syntax"></a>Syntax

> **/Errorreport** \[ **keine** \| **Aufforderung** \| **Warteschlange** **senden \| senden** ]

## <a name="remarks"></a>Bemerkungen

Die **/errorreport** -Argumente werden von den Windows-Fehlerberichterstattung Dienst Einstellungen überschrieben. EDITBIN sendet automatisch Berichte interner Fehler an Microsoft, wenn die Berichterstellung durch Windows-Fehlerberichterstattung aktiviert wird. Wenn Windows-Fehlerberichterstattung deaktiviert ist, wird kein Bericht gesendet.

## <a name="see-also"></a>Weitere Informationen

[EDITBIN-Optionen](editbin-options.md)
