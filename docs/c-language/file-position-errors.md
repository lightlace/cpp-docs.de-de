---
title: Dateipositionsfehler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1bcb4db45f17c9e2d697ee63912e63efe6e8176c
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="file-position-errors"></a>Dateipositionsfehler
**ANSI 4.9.9.1, 4.9.9.4** Der Wert, auf den das Makro `errno` bei einem Fehler durch die `fgetpos`- oder `ftell`-Funktion festgelegt wird  
  
 Wenn `fgetpos` oder `ftell` fehlschlägt, wird `errno` auf die Manifestkonstante `EINVAL` festgelegt, wenn die Position ungültig ist, oder auf `EBADF`, wenn die Dateinummer ungültig ist. Die Konstanten sind in ERRNO.H definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
