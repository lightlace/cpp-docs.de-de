---
title: -TLS | Microsoft Docs
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
ms.openlocfilehash: b5e510f406ceae7508f9b84f99e7ab397d22f114
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="tls"></a>/TLS
Zeigt die IMAGE_TLS_DIRECTORY-Struktur aus einer ausführbaren Datei.  
  
## <a name="remarks"></a>Hinweise  
 / TLS werden die Felder der TLS-Struktur sowie die Adressen der TLS-Rückruffunktionen angezeigt.  
  
 Wenn ein Programm keinen lokalen Threadspeicher verwendet, enthält das Bild nicht TLS-Struktur.  Finden Sie unter [Thread](../../cpp/thread.md) für Weitere Informationen.  
  
 IMAGE_TLS_DIRECTORY wird in "Winnt.h" definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)