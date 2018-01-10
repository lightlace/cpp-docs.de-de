---
title: -TLS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /TLS
dev_langs: C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5adf246e343a16abebdc584589e9633b195444ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tls"></a>/TLS
Zeigt die IMAGE_TLS_DIRECTORY-Struktur aus einer ausführbaren Datei.  
  
## <a name="remarks"></a>Hinweise  
 / TLS werden die Felder der TLS-Struktur sowie die Adressen der TLS-Rückruffunktionen angezeigt.  
  
 Wenn ein Programm keinen lokalen Threadspeicher verwendet, enthält das Bild nicht TLS-Struktur.  Finden Sie unter [Thread](../../cpp/thread.md) für Weitere Informationen.  
  
 IMAGE_TLS_DIRECTORY wird in "Winnt.h" definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)