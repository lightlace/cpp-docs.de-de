---
title: BSCMAKE-Fehler BK1506
ms.date: 11/04/2016
f1_keywords:
- BK1506
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
ms.openlocfilehash: d1f74a90657985a87accc13bc2b576c1d7fd5a4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554699"
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE-Fehler BK1506

'Dateiname' kann nicht geöffnet werden. [: Grund]

BSCMAKE kann die Datei nicht öffnen.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die Datei von einem anderen Prozess gesperrt. Wenn `reason` sagt **Berechtigung verweigert**, den Browser möglicherweise verwenden, wenn Sie die Datei. Schließen Sie das Durchsuchen-Fenster aus, und wiederholen Sie den Build.

1. Ein voller Datenträger.

1. Ein Hardwarefehler.

1. Die angegebene Ausgabedatei hat den gleichen Namen wie ein vorhandenes Unterverzeichnis.