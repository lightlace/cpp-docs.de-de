---
title: Abort-Funktion | Microsoft Docs
ms.custom: 
ms.date: 12/01/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e73c2549e5ce29823376b378b9dc565e2d883ffa
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2018
---
# <a name="abort-function"></a>abort-Funktion

Die **abort** -Funktion, auch in der standardincludedatei deklariert \<stdlib.h >, beendet ein C++-Programm. Der Unterschied zwischen **beenden** und **abort** handelt, **beenden** ermöglicht die C++-Laufzeit Beendigung eine Verarbeitung stattfinden (globale Objekt Destruktoren aufgerufen werden), während **abort** das Programm sofort beendet. Weitere Informationen finden Sie unter [abort](../c-runtime-library/reference/abort.md) in der *Run-Time Library Reference*.

## <a name="see-also"></a>Siehe auch

[Programmbeendigung](../cpp/program-termination.md)