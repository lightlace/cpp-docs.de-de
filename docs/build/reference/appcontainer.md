---
title: /APPCONTAINER
ms.date: 11/04/2016
f1_keywords:
- /APPCONTAINER
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
ms.openlocfilehash: 0805393990070a10caed8208138e31ab9084bdf0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482551"
---
# <a name="appcontainer"></a>/APPCONTAINER

Markiert eine ausführbare Datei, die in einem app-Container ausgeführt werden muss, z. B. ein Microsoft Store oder eine universelle Windows-app.

```

/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Hinweise

Eine ausführbare Datei, bei der die **/APPCONTAINER** -Option festgelegt wurde, kann nur in einem App-Container ausgeführt werden. Das ist die in Windows 8 eingeführte Prozessisolationsumgebung. Für Microsoft Store und universelle Windows-apps muss diese Option festgelegt werden.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)<br/>
[Was ist eine universelle Windows-App?](/windows/uwp/get-started/universal-application-platform-guide)