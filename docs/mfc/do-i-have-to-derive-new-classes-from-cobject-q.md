---
title: Muss ich von CObject neue Klassen ableiten? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51904ac06ae6c2db5586f8dc405f85145c5b1f30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343059"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>Muss ich von CObject neue Klassen ableiten?
Nein, stimmen Sie nicht.  
  
 Leiten Sie eine Klasse von [CObject](../mfc/reference/cobject-class.md) Wenn Sie die Funktionen sie bereitstellt benötigen, z. B. Serialisierung oder dynamische Creatability. Viele Datenklassen müssen in Dateien, serialisiert werden, weshalb es oft eine gute Idee, daraus ableiten kann `CObject`. Ein Beispiel für eine Klasse vom abgeleitet `CObject`, finden Sie unter der [Scribble-Beispiel](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)
