---
title: Dynamische Objekterstellung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5763e3f0f3ee5a0e58ac20fe9f637e4f7e097999
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346645"
---
# <a name="dynamic-object-creation"></a>Dynamische Objekterstellung
In diesem Artikel wird erläutert, wie ein Objekt zur Laufzeit dynamisch erstellt wird. Die Prozedur zur Laufzeit-Klasseninformationen verwendet, wie im Artikel erläutert [zugreifen auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md).  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Ein Objekt, dessen-Klasse zur Laufzeit dynamisch zu erstellen  
  
1.  Verwenden Sie den folgenden Code dynamisch erstellen ein Objekt mithilfe der `CreateObject` Funktion der `CRuntimeClass`. Beachten Sie, dass bei einem Fehler `CreateObject` gibt **NULL** anstatt durch das Auslösen einer Ausnahme:  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CObject](../mfc/using-cobject.md)

