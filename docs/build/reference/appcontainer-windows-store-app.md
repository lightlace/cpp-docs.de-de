---
title: "/APPCONTAINER (Windows Store-App) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /APPCONTAINER (Windows Store-App)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob der Linker ein ausführbares Image erstellt, das in einem App\-Container ausgeführt werden muss.  
  
## Syntax  
  
```  
/APPCONTAINER[:NO]  
```  
  
## Hinweise  
 Die \/APPCONTAINER\-Option ist standardmäßig deaktiviert.  
  
 Diese Option ändert eine ausführbare Datei, um anzugeben, ob die App in der App\-Container\- Prozessisolationsumgebung ausgeführt werden muss.  Geben Sie "\/APPCONTAINER" für eine App an, die in der App\-Containerumgebung ausgeführt werden muss, zum Beispiel für eine [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)]\-App. \(Die Option wird in Visual Studio automatisch festgelegt, wenn Sie eine [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)]\-App mit einer Vorlage erstellen.\) Für eine Desktop\-App geben Sie "\/APPCONTAINER:NO" an, oder Sie lassen die Option einfach weg.  
  
 Die \/APPCONTAINER\-Option wurde in [!INCLUDE[win8](../../build/includes/win8_md.md)] eingeführt.  
  
### So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften**.  
  
3.  Erweitern Sie den Knoten **Linker**.  
  
4.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
5.  Geben Sie in **Zusätzliche Optionen** die Option `/APPCONTAINER` oder `/APPCONTAINER:NO` ein.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)