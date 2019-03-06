---
title: / APPCONTAINER (UWP/Microsoft Store-App)
ms.date: 11/04/2016
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
ms.openlocfilehash: c58559a908a9281507c74c2dd3ff7e56490cb6e3
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418671"
---
# <a name="appcontainer-microsoft-store-app"></a>/ APPCONTAINER (Microsoft Store-App)

Gibt an, ob der Linker ein ausführbares Image erstellt, das in einem App-Container ausgeführt werden muss.

## <a name="syntax"></a>Syntax

```
/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Hinweise

Die /APPCONTAINER-Option ist standardmäßig deaktiviert.

Diese Option ändert eine ausführbare Datei, um anzugeben, ob die App in der App-Container- Prozessisolationsumgebung ausgeführt werden muss. Geben Sie "/ appcontainer" für eine app, die in der App-containerumgebung ausgeführt werden muss, z. B. eine universelle Windows-Plattform (UWP) oder Windows Phone 8.x-app. (Die Option wird automatisch in Visual Studio festgelegt, wenn Sie eine universelle Windows-app aus einer Vorlage erstellen.) Für eine Desktop-App geben Sie "/APPCONTAINER:NO" an, oder Sie lassen die Option einfach weg.

Die/appcontainer-Option wurde in Windows 8 eingeführt.

### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. In **zusätzliche Optionen**, geben Sie `/APPCONTAINER` oder `/APPCONTAINER:NO`.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
