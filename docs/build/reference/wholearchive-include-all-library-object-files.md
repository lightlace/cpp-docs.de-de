---
title: -WHOLEARCHIVE (umfassen alle Bibliotheksdateien Objekt) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed12541eeb0c85b2d218a7a5f3305413d4dc2ec8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="wholearchive-include-all-library-object-files"></a>/ WHOLEARCHIVE (umfassen alle Bibliotheksdateien-Objekt)
Erzwingen, dass des Linkers die statische Bibliothek in der verknüpften ausführbaren Datei alle Objektdateien einschließt.  
  
## <a name="syntax"></a>Syntax  
  
> / WHOLEARCHIVE [:*Bibliothek*]  
  
## <a name="remarks"></a>Hinweise  
  
Die /WHOLEARCHIVE-Option erzwingt, dass den Linker Includedatei jedes Objekt entweder aus einer angegebenen statische Bibliothek, oder wenn keine Bibliothek angegeben ist, über alle statischen Bibliotheken, die auf den LINK angegebene Befehl. Um die /WHOLEARCHIVE-Option für mehrere Bibliotheken angeben, können Sie mehrere /WHOLEARCHIVE Switches in der Linker-Befehlszeile. Standardmäßig enthält der Linker Objektdateien in der verknüpften Ausgabe, nur dann, wenn sie Symbole verwiesen wird, indem Sie andere Objektdateien in der ausführbaren Datei exportieren. Die /WHOLEARCHIVE-Option bewirkt, dass den Linker behandeln alle Objektdateien, die in einer statischen Bibliothek archiviert werden, als ob sie einzeln in der Linker-Befehlszeile angegeben wurden.  
  
Die /WHOLEARCHIVE-Option kann verwendet werden, um alle Symbole aus einer statischen Bibliothek erneut exportieren. Dadurch können Sie sicherstellen, dass alle Ihre Bibliothekscode, Ressourcen und Metadaten enthalten sind, wenn Sie eine Komponente aus mehr als eine statische Bibliothek erstellen. Wenn Warnung LNK4264 beim Erstellen einer statischen Bibliothek, die Windows-Runtime-Komponenten für den Export enthält angezeigt wird, verwenden Sie die /WHOLEARCHIVE-Option, wenn diese Bibliothek in eine andere Komponente oder app verknüpfen.  
  
Die /WHOLEARCHIVE-Option wurde in Visual Studio 2015 Update 2 eingeführt.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
1.  Wählen Sie die **Befehlszeile** Eigenschaftenseite unter **Konfigurationseigenschaften**, **Linker**.  
  
1.  Fügen Sie der /WHOLEARCHIVE-Option aus, um die **Zusatzoptionen** Textfeld.  
  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)