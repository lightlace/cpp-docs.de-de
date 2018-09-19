---
title: -APPCONTAINER | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /APPCONTAINER
dev_langs:
- C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d8e19724183963329b959286a996b4f21d18b4c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709178"
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