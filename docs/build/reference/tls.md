---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: 1760e94046a950f67d3c3fd7ef13aa40ca7de47a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417787"
---
# <a name="tls"></a>/TLS

Zeigt die Struktur IMAGE_TLS_DIRECTORY aus einer ausführbaren Datei an.

## <a name="remarks"></a>Hinweise

/ TLS werden die Felder der TLS-Struktur sowie die Adressen der TLS-Rückruffunktionen angezeigt.

Wenn ein Programm keinen threadlokalen Speicher verwendet, enthält das Image keine TLS-Struktur.  Finden Sie unter [Thread](../../cpp/thread.md) für Weitere Informationen.

IMAGE_TLS_DIRECTORY wird in "Winnt.h" definiert.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)
