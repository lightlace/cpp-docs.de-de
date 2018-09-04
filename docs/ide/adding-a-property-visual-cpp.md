---
title: Hinzufügen einer Eigenschaft (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e121cf9738910b105f5bb1933592e67d334f8937
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685325"
---
# <a name="adding-a-property-visual-c"></a>Hinzufügen einer lokalen Eigenschaft (Visual C++)
Sie können den [Assistenten zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md) verwenden, um einer Schnittstelle in Ihrem Projekt eine Eigenschaft hinzuzufügen.  
  
### <a name="to-add-a-property-to-your-object"></a>So fügen Sie Ihrem Objekt eine Eigenschaft hinzu  
  
1.  Klicken Sie in der [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) mit der rechten Maustaste auf den Namen der Schnittstelle, der die Eigenschaft hinzugefügt werden soll.  
  
    > [!NOTE]
    >  Sie können Eigenschaften auch zu Disp-Schnittstellen hinzufügen, die im Bibliotheksknoten geschachtelt sind, sofern das Projekt nicht attributiert ist.  
  
2.  Klicken Sie im Kontextmenü auf die Option **Hinzufügen**, und klicken Sie danach auf **Eigenschaft hinzufügen**.  
  
3.  Geben Sie im [Assistenten zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md) die Informationen zum Erstellen der Eigenschaft an.  
  
4.  Geben Sie alle Einstellungen der Interface Definiton Language dieser Eigenschaft auf der Seite [IDL-Attribute](../ide/idl-attributes-add-property-wizard.md) des Assistenten an.  
  
5.  Klicken Sie auf **Fertig stellen**, um die Eigenschaft hinzuzufügen.  
  
 Die Methoden **Get** und `Put` der Eigenschaft werden in der Klassenansicht als zwei Symbole unter der Schnittstelle angezeigt, in der sie definiert sind. Sie können eines der Symbole doppelklicken, um die Eigenschaftsdeklaration in der IDL-Datei anzuzeigen.  
  
-   Bei ATL-Schnittstellen werden die Funktionen **Get** und **Put** der CPP-Datei hinzugefügt, und Verweise auf diese Funktionen werden der H-Datei hinzugefügt.  
  
-   Wenn Sie bei MFC-Disp-Schnittstellen **Membervariable** als Implementierungstyp auswählen, werden der implementierenden Klasse eine Methode und eine Variable hinzugefügt. Wenn Sie die **Get/Set-Methoden** als Implementierungstyp auswählen, werden der implementierenden Klasse zwei Methoden hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Creating a COM Interface (Erstellen einer COM-Schnittstelle)](../ide/creating-a-com-interface-visual-cpp.md)   
 [Editing a COM Interface (Bearbeiten einer COM-Schnittstelle)](../ide/editing-a-com-interface.md)   
 [The Component Object Model (Das Component Object Model)](/windows/desktop/com/the-component-object-model)   
 [Interface Pointers and Interfaces (Schnittstellenzeiger und Schnittstellen)](/windows/desktop/com/interface-pointers-and-interfaces)