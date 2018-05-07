---
title: Bearbeiten einer COM-Schnittstelle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.editing.interfaces
dev_langs:
- C++
helpviewer_keywords:
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd7a61593a1024c00c0fd0de6bd62ff3ee9323b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="editing-a-com-interface"></a>Bearbeiten einer COM-Schnittstelle
Mithilfe der Befehle im Kontextmenü Klassenansicht können Sie neue Methoden und Eigenschaften für die COM-Schnittstellen in Visual C++-Projekten definieren. Darüber hinaus können Sie Ereignisse für ActiveX-Steuerelemente aus der Toolbox definieren.  
  
 Für ATL und MFC-basierten COM Objektklassen können Sie die Implementierung der Klasse zur gleichen Zeit bearbeiten, die Schnittstelle zu bearbeiten.  
  
> [!NOTE]
>  Bei Schnittstellen, die Sie außerhalb von definiert haben die **Klasse hinzufügen** (Dialogfeld), Visual C++ fügt die Methoden oder Eigenschaften der IDL-Datei, und es Stubs hinzufügen, um die Klassen, Methoden zu implementieren, selbst wenn die Schnittstellen manuell hinzugefügt werden.  
  
 Die folgenden drei Assistenten können Sie die vorhandene Schnittstellen anpassen. Sie sind in der Klassenansicht verfügbar:  
  
|Assistent|Projekttyp:|  
|------------|------------------|  
|[Fügen Sie der Assistent zum Eigenschaften hinzu](../ide/names-add-property-wizard.md)|ATL- oder MFC-Projekten, die Unterstützung von ATL Klicken Sie auf die Schnittstelle, die Sie die Eigenschaft hinzufügen möchten.<br /><br /> Visual C++ erkennt den Projekttyp und ändert die Optionen des Assistenten zum Hinzufügen einer Eigenschaft entsprechend:<br /><br /> – Für Disp-Schnittstellen in Projekten, die mithilfe von erstellt die [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md), den Assistenten zum Hinzufügen einer Eigenschaft aufrufen bietet Optionen, die bestimmten mit MFC.<br />– Für MFC-ActiveX-Steuerelement-Schnittstellen bietet der Assistent zum Hinzufügen von Eigenschaften eine Liste von vordefinierten Methoden und Eigenschaften, die Sie verwenden, wie bereitgestellt oder für das Steuerelement angepasst.<br />– Für alle anderen Schnittstellen bieten die Eigenschaft-Assistenten Optionen, die in den meisten Situationen nützlich.|  
|[Assistent zum Hinzufügen von Methoden](../ide/add-method-wizard.md)|ATL- oder MFC-Projekten, die Unterstützung von ATL Klicken Sie auf die Schnittstelle, die Sie die Methode hinzufügen möchten.<br /><br /> Visual C++ erkennt den Projekttyp und ändert die Optionen des Assistenten zum Hinzufügen einer Methode entsprechend:<br /><br /> – Für Disp-Schnittstellen in Projekten, die erstellt werden, mithilfe der [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md), Aufrufen des Assistenten zum Hinzufügen einer Methode bietet Optionen, die bestimmten mit MFC.<br />– Für MFC-ActiveX-Steuerelement-Schnittstellen enthält den Assistenten zum Hinzufügen einer Methode eine Liste von vordefinierten Methoden und Eigenschaften, die Sie verwenden, wie bereitgestellt oder für das Steuerelement angepasst.<br />– Für alle anderen Schnittstellen der **Methode hinzufügen** Assistenten bieten Optionen, die in den meisten Situationen nützlich.|  
  
 Darüber hinaus können Sie neue Schnittstellen auch auf das COM-Steuerelement implementieren, indem Steuerelementklasse für das Objekt in der Klassenansicht mit der rechten Maustaste, und klicken Sie auf [Schnittstelle implementieren](../ide/implement-interface-wizard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C++-Projekttypen](../ide/visual-cpp-project-types.md)