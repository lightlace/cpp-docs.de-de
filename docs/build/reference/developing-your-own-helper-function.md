---
title: Entwickeln eigener Hilfsfunktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6b8e397fecc8f14140cd7c86217421d5aa1a749
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371397"
---
# <a name="developing-your-own-helper-function"></a>Entwickeln eigener Hilfsfunktionen
Sie möchten eine eigene Version der Routine zur spezifischen Verarbeitung basierend auf den Namen der DLL oder Importe sind bereitstellen. Es gibt zwei Methoden, die Auswirkungen dieses: eigene Codierung, meist basierend auf den angegebenen Code oder lediglich die angegebene Version mit der zuvor beschriebenen Benachrichtigungshooks einbinden.  
  
 Ihren eigenen Code  
 Dies ist recht einfach, da Sie den angegebenen Code im Wesentlichen als Richtlinie für das neue Projekt verwenden können. Natürlich müssen sie die Aufrufkonventionen entsprechen, und wenn zu den vom Linker generierte Thunks zurückgegeben wird, müssen sie einen geeigneten Funktionszeiger zurückgeben. Einmal in Ihrem Code möglich beide Wege sind nahezu beliebig um den Aufruf erfüllen, oder rufen aus dem Aufruf.  
  
 Verwenden Sie die Verarbeitungsbeginn  
 Sie werden wahrscheinlich am einfachsten, geben Sie einfach einen neuen Zeiger auf eine Benachrichtigung Benutzer bereitgestellte Hookfunktion, die die gleichen Werte wie das Standard-Hilfsobjekt, über die DliStartProcessing empfängt. An diesem Punkt kann die Hookfunktion im Wesentlichen werden für die neue Hilfsfunktion wie eine erfolgreiche Rückgabe für die Hilfe standardmäßig alle weiteren Verarbeitung in der Hilfsfunktion umgangen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)