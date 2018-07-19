---
title: Funktionstypen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 322bd45abbfe217671fd39f0617987fde21445db
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367650"
---
# <a name="function-types"></a>Funktionstypen
Es gibt im Wesentlichen zwei Arten von Funktionen. Eine Funktion, die einen Stapelrahmen erfordert, wird eine Frame-Funktion aufgerufen. Eine Funktion, die nicht über einen Stapelrahmen erfordert, wird eine Blattebene-Funktion aufgerufen.  
  
 Eine Frame-Funktion ist eine Funktion, die Stapelspeicher zuweist, andere Funktionen aufruft, um nicht flüchtigen Register speichert oder mithilfe der Ausnahmebehandlung. Darüber hinaus wird eine Tabelle Funktionsstart erforderlich. Eine Frame-Funktion erfordert einen Prolog und einen Epilog. Eine Funktion Frame Stapelspeicher dynamisch zuweisen und Frame-Pointer verwenden. Eine Frame-Funktion weist die vollen Fähigkeiten der dies verfügbare standard aufrufen.  
  
 Wenn eine Frame-Funktion nicht eine andere Funktion aufruft, muss es ist nicht erforderlich, um den Stapel auszurichten (Siehe den Abschnitt [Stapelzuordnung](../build/stack-allocation.md)).  
  
 Eine Blattebene-Funktion ist eine, die eine Tabelle Funktionsstart nicht erfordert. Sie können Änderungen vornehmen, um alle nicht flüchtigen Register, einschließlich RSP, was bedeutet, dass keine Funktionen aufrufen oder Stapelspeicher reservieren. Es ist zulässig, den Stapel nicht ausgerichteten lassen, während sie ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwendung von Stapeln](../build/stack-usage.md)
