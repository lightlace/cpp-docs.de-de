---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: c125a6439e6cda2159a8bde2317528e667eaf310
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532634"
---
# <a name="tls"></a>/TLS

Zeigt die Struktur IMAGE_TLS_DIRECTORY aus einer ausführbaren Datei an.

## <a name="remarks"></a>Hinweise

/ TLS werden die Felder der TLS-Struktur sowie die Adressen der TLS-Rückruffunktionen angezeigt.

Wenn ein Programm keinen threadlokalen Speicher verwendet, enthält das Image keine TLS-Struktur.  Finden Sie unter [Thread](../../cpp/thread.md) für Weitere Informationen.

IMAGE_TLS_DIRECTORY wird in "Winnt.h" definiert.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)