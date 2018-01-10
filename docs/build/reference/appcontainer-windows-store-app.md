---
title: -APPCONTAINER (Windows Store-App) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22ca7bec885f20518950626d33f7e3af553d0d52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="appcontainer-windows-store-app"></a>/APPCONTAINER (Windows Store-App)
Gibt an, ob der Linker ein ausführbares Image erstellt, das in einem App-Container ausgeführt werden muss.  
  
## <a name="syntax"></a>Syntax  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die /APPCONTAINER-Option ist standardmäßig deaktiviert.  
  
 Diese Option ändert eine ausführbare Datei, um anzugeben, ob die App in der App-Container- Prozessisolationsumgebung ausgeführt werden muss. Geben Sie "/APPCONTAINER" für eine App an, die in der App-Containerumgebung ausgeführt werden muss, zum Beispiel für eine [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)]-App. (Die Option wird in Visual Studio automatisch festgelegt, wenn Sie eine [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)]-App mit einer Vorlage erstellen.) Für eine Desktop-App geben Sie "/APPCONTAINER:NO" an, oder Sie lassen die Option einfach weg.  
  
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