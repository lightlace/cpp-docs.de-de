---
title: Dynamische Objekterstellung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3ac2371e6f9e8a4ba351b482b50f347bee164e02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="dynamic-object-creation"></a>Dynamische Objekterstellung
In diesem Artikel wird erläutert, wie ein Objekt zur Laufzeit dynamisch erstellt wird. Die Prozedur zur Laufzeit-Klasseninformationen verwendet, wie im Artikel erläutert [zugreifen auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md).  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Ein Objekt, dessen-Klasse zur Laufzeit dynamisch zu erstellen  
  
1.  Verwenden Sie den folgenden Code dynamisch erstellen ein Objekt mithilfe der `CreateObject` Funktion der `CRuntimeClass`. Beachten Sie, dass bei einem Fehler `CreateObject` gibt **NULL** anstatt durch das Auslösen einer Ausnahme:  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CObject](../mfc/using-cobject.md)

