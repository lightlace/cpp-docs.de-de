---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: 751c212398f3d309b1d31d204291fe3a0503cf06
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811861"
---
# <a name="tls"></a>/TLS

Zeigt die Struktur IMAGE_TLS_DIRECTORY aus einer ausführbaren Datei an.

## <a name="remarks"></a>Hinweise

/ TLS werden die Felder der TLS-Struktur sowie die Adressen der TLS-Rückruffunktionen angezeigt.

Wenn ein Programm keinen threadlokalen Speicher verwendet, enthält das Image keine TLS-Struktur.  Finden Sie unter [Thread](../../cpp/thread.md) für Weitere Informationen.

IMAGE_TLS_DIRECTORY wird in "Winnt.h" definiert.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)
