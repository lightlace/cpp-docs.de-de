---
title: Stabilität
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
ms.openlocfilehash: f41fc019c6a1779362644e29c5518d40690fe9db
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500673"
---
# <a name="robustness"></a>Stabilität

Verwenden Sie die folgenden C-Laufzeitbibliotheksfunktionen, um die Stabilität des Programms zu verbessern.

## <a name="run-time-robustness-functions"></a>Funktionen für die Laufzeitstabilität

|Funktion|Verwendung|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Übergibt die Steuerung an den Fehlerbehandlungsmechanismus, wenn der **new**-Operator keine Speicherbelegung vornehmen kann.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Behandelt Win32-Ausnahmen (C-strukturierte Ausnahmen) als C++-typisierte Ausnahmen.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installiert Ihre eigene Beendigungsfunktion, die von [terminate](../c-runtime-library/reference/terminate-crt.md) aufgerufen werden soll.|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installiert Ihre eigene Beendigungsfunktion, die von [unexpected](../c-runtime-library/reference/unexpected-crt.md) aufgerufen werden soll.|

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
[SetUnhandledExceptionFilter](/win32/api/errhandlingapi/nf-errhandlingapi-setunhandledexceptionfilter)<br/>
