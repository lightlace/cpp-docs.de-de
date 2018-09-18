---
title: Weitere Überlegungen zur Beendigung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: acbe2332-9d8a-4a58-a471-dd652a837384
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f7b3c12c5889265ebb06e199c7f1e1e3cb440b4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034069"
---
# <a name="additional-termination-considerations"></a>Weitere Überlegungen zur Beendigung

Sie können ein C++-Programm beenden, mithilfe von `exit`, **zurückgeben**, oder `abort`. Mit der Funktion `atexit` können Sie eine Beendigung der Verarbeitung hinzufügen. Diese Funktionen werden in den folgenden Abschnitten beschrieben.

## <a name="see-also"></a>Siehe auch

[Starten und Beenden](../cpp/startup-and-termination-cpp.md)