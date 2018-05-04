---
title: / APPCONTAINER (universelle Windows-Plattform/Microsoft Store-App) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca1a3ed5adaada689d374eeb3e67bae6c989e0b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
  
 Die /APPCONTAINER-Option wurde in [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] eingeführt.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
5.  In **Zusatzoptionen**, geben Sie `/APPCONTAINER` oder `/APPCONTAINER:NO`.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)