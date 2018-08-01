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
ms.openlocfilehash: 54780b11e07819ca78eba89d9af5a8ba018cc9e4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401807"
---
# <a name="additional-termination-considerations"></a>Weitere Überlegungen zur Beendigung
Sie können ein C++-Programm beenden, mithilfe von `exit`, **zurückgeben**, oder `abort`. Mit der Funktion `atexit` können Sie eine Beendigung der Verarbeitung hinzufügen. Diese Funktionen werden in den folgenden Abschnitten beschrieben.  
  
## <a name="see-also"></a>Siehe auch  
 [Starten und Beenden](../cpp/startup-and-termination-cpp.md)