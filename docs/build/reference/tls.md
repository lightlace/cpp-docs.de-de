---
title: -TLS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /TLS
dev_langs:
- C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78f485a783dbe8b5fe9a49ed3100754115bf50b8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714653"
---
# <a name="tls"></a>/TLS

Zeigt die Struktur IMAGE_TLS_DIRECTORY aus einer ausführbaren Datei an.

## <a name="remarks"></a>Hinweise

/ TLS werden die Felder der TLS-Struktur sowie die Adressen der TLS-Rückruffunktionen angezeigt.

Wenn ein Programm keinen threadlokalen Speicher verwendet, enthält das Image keine TLS-Struktur.  Finden Sie unter [Thread](../../cpp/thread.md) für Weitere Informationen.

IMAGE_TLS_DIRECTORY wird in "Winnt.h" definiert.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)