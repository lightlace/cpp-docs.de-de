---
title: Abort-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/01/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e5679ce718c564ee40fb07b676756ef79344a99
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403621"
---
# <a name="abort-function"></a>abort-Funktion

Die **Abbrechen** -Funktion, auch in der standardincludedatei deklariert \<stdlib.h >, beendet ein C++-Programm. Der Unterschied zwischen `exit` und **Abbrechen** ist, die `exit` ermöglicht die Verarbeitung der C++-Laufzeit-Beendigung durchzuführen (globale Objekt Destruktoren aufgerufen werden), während **Abbrechen** das Programm beendet sofort. Weitere Informationen finden Sie unter [Abbrechen](../c-runtime-library/reference/abort.md) in die *Run-Time Library Reference*.

## <a name="see-also"></a>Siehe auch
[Programmbeendigung](../cpp/program-termination.md)