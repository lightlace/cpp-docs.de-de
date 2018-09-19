---
title: BSCMAKE-Fehler BK1506 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26201a894212701cca19ab2192676b37a69e8b57
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088695"
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE-Fehler BK1506

'Dateiname' kann nicht geöffnet werden. [: Grund]

BSCMAKE kann die Datei nicht öffnen.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die Datei von einem anderen Prozess gesperrt. Wenn `reason` sagt **Berechtigung verweigert**, den Browser möglicherweise verwenden, wenn Sie die Datei. Schließen Sie das Durchsuchen-Fenster aus, und wiederholen Sie den Build.

1. Ein voller Datenträger.

1. Ein Hardwarefehler.

1. Die angegebene Ausgabedatei hat den gleichen Namen wie ein vorhandenes Unterverzeichnis.