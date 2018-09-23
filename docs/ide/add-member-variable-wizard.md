---
title: Assistent zum Hinzufügen von Membervariablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.variable.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d4518a48d51e6187015dc3fd7b5456e04e1ae84
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701531"
---
# <a name="add-member-variable-wizard"></a>Assistent zum Hinzufügen von Membervariablen
Dieser Assistent fügt die Deklaration einer Membervariable zur Headerdatei und abhängig von den Optionen Code zur CPP-Datei hinzu. Sobald Sie eine Membervariable mithilfe des Assistenten hinzugefügt haben, können Sie den Code in der Entwicklungsumgebung bearbeiten.  
  
- **Zugriff**

   Legt den Zugriff auf die Membervariable fest. Bei Zugriffsmodifizierern handelt es sich um Schlüsselwörter, die den Zugriff festlegen, den andere Klassen auf die Membervariable haben. Weitere Informationen zum Festlegen des Zugriffs finden Sie unter [Member-Access Control (Steuerung des Memberzugriffs)](../cpp/member-access-control-cpp.md). Standardmäßig wird die Zugriffsebene von Membervariablen auf **public** festgelegt.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
- **Variablentyp**

   Legt den Rückgabetyp für die hinzugefügte Membervariable fest.  
  
   - Wenn Sie eine Membervariable hinzufügen, bei der es sich nicht um ein Steuerelement für Dialogfelder handelt, wählen Sie den Typ aus der Liste der verfügbaren Typen aus.  
  
      Weitere Informationen zu Typen finden Sie unter [Grundlegende Typen](../cpp/fundamental-types-cpp.md).  
  
      |||  
      |-|-|  
      |**char**|**short**|  
      |**double**|**unsigned char**|  
      |**float**|**unsigned int**|  
      |**int**|**unsigned long**|  
      |**long**||  
  
   - Wenn Sie eine Membervariable für ein Steuerelement für Dialogfelder hinzufügen, wird dieses Feld mit dem Typ des Objekts aufgefüllt, das für ein Steuerelement oder einen Wert zurückgegeben wird. Wenn Sie **Steuerelement** auswählen, gibt der **Variablentyp** die Basisklasse des Steuerelements an, das Sie im Feld **Steuerelement-ID** ausgewählt haben. Wenn das Steuerelement für ein Dialogfeld einen Wert enthalten kann und Sie **Wert** ausgewählt haben, gibt der **Variablentyp** den geeigneten Typ für den Wert an, den das Steuerelement enthalten kann. Weitere Informationen finden Sie unter [Dialog Box Controls and Variable Types (Steuerelemente für Dialogfelder und Variablentypen)](../ide/dialog-box-controls-and-variable-types.md).  
  
      Dieser Wert hängt von der Auswahl in **Steuerelement-ID** ab und kann nicht geändert werden.  
  
- **Variablenname**

   Legt den Namen der hinzugefügten Membervariable fest. Membervariable beginnen üblicherweise mit der Identifizierungszeichenfolge „m_,“, die in der Regel standardmäßig bereitgestellt wird.  
  
- **Steuerelementvariable**

   Gibt an, dass die Membervariable ein Steuerelement innerhalb eines Dialogfelds mit Unterstützung für [Datenaustausch und Datenvalidierung](../mfc/dialog-data-exchange-and-validation.md) verwaltet. Weitere Informationen finden Sie unter [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange). Diese Option ist nur für Membervariablen verfügbar, die zu Klassen hinzugefügt wurden, die von [CDialog](../mfc/reference/cdialog-class.md) abgeleitet wurden. Aktivieren Sie dieses Kontrollkästchen, um die Optionen **Steuerelement-ID** und **Steuerelementtyp** zu aktivieren.  
  
- **Steuerelement-ID**

   Legt die ID für die Steuerelementvariable fest, die Sie hinzufügen. Wählen Sie die ID für den Typ des Steuerelements, für den Sie die Membervariable hinzufügen, aus der Liste aus. Diese Liste ist nur aktiv, wenn das Kontrollkästchen **Steuerelementvariable** aktiviert und auf die Steuerelement-IDs beschränkt ist, die bereits zum Dialogfeld hinzugefügt wurden. Für die Standardschaltfläche **OK** entspricht die Steuerelement-ID beispielsweise **IDOK**.  
  
   |Option|Beschreibung |  
   |------------|-----------------|  
   |**Steuerelement**|Diese Option ist standardmäßig für den Steuerelementtyp festgelegt. Sie verwaltet das Steuerelement, nicht dessen Status oder Inhalte (wie es bei einem Listenfeld, einem Kombinationsfeld oder einem Bearbeitungsfeld möglicherweise gewünscht ist).|  
   |**Wert**|Diese Option ist nur für Steuerelementtypen verfügbar, die einen Wert enthalten können (z.B. ein Bearbeitungsfeld) oder einen Status wiedergeben (z.B. ein Kontrollkästchen), und für die Sie den Bereich, die Inhalte und den Status verwalten möchten. Weitere Informationen finden Sie unter [Dialog Box Controls and Variable Types (Steuerelemente für Dialogfelder und Variablentypen)](../ide/dialog-box-controls-and-variable-types.md).|  
  
- **Kategorie**

   Gibt an, ob die Variable auf einem Steuerelementtyp oder auf dem Wert des Steuerelements basiert.  
  
- **Steuerelementtyp**

   Legt den Typ des Steuerelements fest, das hinzugefügt wird. Dieses Feld kann nicht geändert werden. Eine Schaltfläche hat beispielsweise den Steuerelementtyp **BUTTON**, und ein Kombinationsfeld hat den Steuerelementtyp **COMBOBOX**. Weitere Informationen finden Sie unter [Dialog Box Controls and Variable Types (Steuerelemente für Dialogfelder und Variablentypen)](../ide/dialog-box-controls-and-variable-types.md).  
  
- **Maximale Zeichenanzahl**

   Nur verfügbar, wenn der **Variablentyp** auf [CString](../atl-mfc-shared/reference/cstringt-class.md) festgelegt ist. Gibt die maximale Anzahl von Zeichen an, die das Steuerelement enthalten kann.  
  
- **Mindestwert**

   Nur verfügbar, wenn der Variablentyp **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, [COLECurrency](../mfc/reference/colecurrency-class.md) oder [CTime](../atl-mfc-shared/reference/ctime-class.md) ist. Gibt den niedrigsten Wert an, der für eine Skalierung oder einen Datenbereich akzeptiert wird.  
  
- **Höchstwert**

   Nur verfügbar, wenn der Variablentyp **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, `COLECurrency` oder `CTime` ist. Gibt den höchsten Wert an, der für eine Skalierung oder einen Datenbereich akzeptiert wird.  
  
- **H-Datei**

   Gibt für ActiveX-Steuerelemente an, welche Membervariablen einer Wrapperklasse erfordern. Legt den Namen der Headerdatei fest, die zur Klassendeklaration hinzugefügt werden soll.  
  
- **CPP-Datei**

   Gibt für ActiveX-Steuerelemente an, welche Membervariablen einer Wrapperklasse erfordern. Legt den Namen der Implementierungsdatei fest, die zur Klassendefinition hinzugefügt werden soll.  
  
- **Kommentar**

   Fügt einen Kommentar zur Headerdatei der Membervariable hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [Adding a Member Variable (Hinzufügen einer Membervariablen)](../ide/adding-a-member-variable-visual-cpp.md)