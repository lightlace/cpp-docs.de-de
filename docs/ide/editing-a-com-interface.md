---
title: Bearbeiten einer COM-Schnittstelle | Microsoft-Dokumentation
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338681"
---
# <a name="editing-a-com-interface"></a>Bearbeiten einer COM-Schnittstelle
Mithilfe der Befehle des Kontextmenüs der Klassenansicht können Sie neue Methoden und Eigenschaften für die COM-Schnittstellen in Ihren Visual C++-Projekten definieren. Darüber hinaus können Sie mit der Toolbox Ereignisse für ActiveX-Steuerelemente definieren.  
  
 Bei ATL- und MFC-basierten COM-Objektklassen können Sie die Implementierung der Klasse und die Schnittstelle zur gleichen Zeit bearbeiten.  
  
> [!NOTE]
>  Für Schnittstellen, die Sie außerhalb des Dialogfelds **Klasse hinzufügen** definiert haben, fügt Visual C++ die Methoden oder Eigenschaften der IDL-Datei und Stubs den Klassen hinzu, die Methoden implementieren, auch wenn die Schnittstellen manuell hinzugefügt werden.  
  
 Die folgenden drei Assistenten unterstützen Sie beim Anpassen vorhandener Schnittstellen. Sie sind in der Klassenansicht verfügbar:  
  
|Assistent|Projekttyp:|  
|------------|------------------|  
|[Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md)|ATL- oder MFC-Projekte, die ATL unterstützen. Klicken Sie mit der rechten Maustaste auf die Schnittstelle, der die Eigenschaft hinzugefügt werden soll.<br /><br /> Visual C++ erkennt den Projekttyp und ändert die Optionen im Assistenten zum Hinzufügen von Eigenschaften entsprechend:<br /><br /> – Für Disp-Schnittstellen in Projekten, die mit dem [MFC-Anwendungs-Assistenten](../mfc/reference/mfc-application-wizard.md) erstellt wurden, stellt das Aufrufen des Assistenten zum Hinzufügen von Eigenschaften MFC-spezifische Optionen bereit.<br />– Für ActiveX-Steuerelementschnittstellen stellt der Assistent zum Hinzufügen von Eigenschaften eine Liste vordefinierter Methoden und Eigenschaften bereit, die Sie verwenden oder für Ihr Steuerelement anpassen können.<br />– Für alle anderen Schnittstellen stellt der Assistent zum Hinzufügen von Eigenschaften Optionen bereit, die in den meisten Situationen nützlich sind.|  
|[Assistent zum Hinzufügen von Methoden](../ide/add-method-wizard.md)|ATL- oder MFC-Projekte, die ATL unterstützen. Klicken Sie mit der rechten Maustaste auf die Schnittstelle, der die Methode hinzugefügt werden soll.<br /><br /> Visual C++ erkennt den Projekttyp und ändert die Optionen im Assistenten zum Hinzufügen von Methoden entsprechend:<br /><br /> – Für Disp-Schnittstellen in Projekten, die mit dem [MFC-Anwendungs-Assistenten](../mfc/reference/mfc-application-wizard.md) erstellt wurden, stellt das Aufrufen des Assistenten zum Hinzufügen von Methoden MFC-spezifische Optionen bereit.<br />– Für ActiveX-Steuerelementschnittstellen stellt der Assistent zum Hinzufügen von Methoden eine Liste vordefinierter Methoden und Eigenschaften bereit, die Sie verwenden oder für Ihr Steuerelement anpassen können.<br />– Für alle anderen Schnittstellen stellt der **Assistent zum Hinzufügen von Methoden** Optionen bereit, die in den meisten Situationen nützlich sind.|  
  
 Darüber hinaus können Sie neue Schnittstellen in Ihrem COM-Steuerelement implementieren, indem Sie in der Klassenansicht mit der rechten Maustaste auf die Steuerelementklasse des Objekts klicken, klicken Sie dann auf [Schnittstelle implementieren](../ide/implement-interface-wizard.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Working with Resource Files (Arbeiten mit Ressourcendateien)](../windows/working-with-resource-files.md)   
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C++-Projekttypen](../ide/visual-cpp-project-types.md)