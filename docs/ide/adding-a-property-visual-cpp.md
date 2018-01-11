---
title: "Hinzufügen einer Eigenschaft (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33fc8c3b5528c0ced4e0d402aec48791b7fbcb9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-property-visual-c"></a>Hinzufügen einer lokalen Eigenschaft (Visual C++)
Sie können die [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md) eine Methode einer Schnittstelle in Ihrem Projekt hinzufügen.  
  
### <a name="to-add-a-property-to-your-object"></a>So fügen Sie eine Eigenschaft für Ihr Objekt hinzu  
  
1.  In [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), mit der rechten Maustaste in des Namens der Schnittstelle, die Sie die Eigenschaft hinzufügen möchten.  
  
    > [!NOTE]
    >  Sie können Eigenschaften auch Dispatchschnittstellen hinzufügen, es sei denn, das Projekt attributiert ist, den Bibliotheksknoten geschachtelt sind.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
3.  In der [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md), geben Sie die Informationen zum Erstellen der Eigenschaft.  
  
4.  Geben Sie alle Interface Definition Language (IDL)-Einstellungen für die Eigenschaft in der [IDL-Attribute](../ide/idl-attributes-add-property-wizard.md) Seite des Assistenten.  
  
5.  Klicken Sie auf **Fertig stellen** die Eigenschaft hinzufügen.  
  
 Die **abrufen** und `Put` Methoden der Eigenschaft werden die Schnittstelle, wo er definiert, zwei Symbole in der Klassenansicht angezeigt. Sie können entweder Symbol zum Anzeigen der Eigenschaftendeklaration in der IDL-Datei doppelklicken.  
  
-   Für ATL-Schnittstellen die **abrufen** und **Put** Funktionen der CPP-Datei hinzugefügt werden, und Verweise auf diese Funktionen die .h-Datei hinzugefügt werden.  
  
-   Für MFC-Dispatchschnittstellen, wenn Sie die Option **Membervariable** als den Implementierungstyp eine Methode und eine Variable auf die Klasse, die ihn implementiert hinzugefügt werden. Bei Auswahl des **Get/Set-Methoden** als den Implementierungstyp zwei Methoden hinzugefügt werden, auf die Klasse, die ihn implementiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer COM-Schnittstelle](../ide/creating-a-com-interface-visual-cpp.md)   
 [Bearbeiten einer COM-Schnittstelle](../ide/editing-a-com-interface.md)   
 [Das Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [Schnittstellenzeiger und Schnittstellen](http://msdn.microsoft.com/library/windows/desktop/ms688484)