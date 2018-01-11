---
title: "Member Assistent zum Hinzufügen von | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.variable.overview
dev_langs: C++
helpviewer_keywords: Add Member Variable Wizard [C++]
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b909ec7ccd830e088df81ca0b2db8cda133c7a20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="add-member-variable-wizard"></a>Assistent zum Hinzufügen von Membervariablen
Dieser Assistent fügt einer Membervariablendeklaration der Headerdatei hinzu, und abhängig von den Optionen können sie Code hinzufügen, in der CPP-Datei. Nachdem Sie die Membervariable, die mit dem Assistenten hinzugefügt haben, können Sie den Code in der Entwicklungsumgebung bearbeiten.  
  
 **Zugriff**  
 Legt den Zugriff auf die Membervariable fest. Zugriffsmodifizierer sind Schlüsselwörter, die angeben, den Zugriff auf die Membervariable haben andere Klassen. Finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md) für Weitere Informationen zum Zugriff angeben. Die Zugriffsebene für die Membervariable auf festgelegt ist **öffentlichen** standardmäßig.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **Variablentyp**  
 Legt den Rückgabetyp für die Membervariable, die Sie hinzufügen.  
  
-   Wenn Sie eine Membervariable, die sich nicht um ein Dialogfeld-Steuerelement ist hinzufügen, wählen Sie aus der Liste der verfügbaren Typen.  
  
     Informationen zu den Typen finden Sie unter [grundlegende Typen](../cpp/fundamental-types-cpp.md).  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   Wenn Sie eine Membervariable für ein Dialogfeld-Steuerelement hinzufügen, wird dieses Feld mit dem Typ des Objekts, die für ein Steuerelement oder ein Wert zurückgegeben gefüllt. Bei Auswahl des **Steuerelement**, klicken Sie dann **Variablentyp** gibt die Basisklasse des Steuerelements, die Sie, in Auswählen der **Kontroll-ID** Feld. Wenn das Dialogfeld-Steuerelement einen Wert enthalten kann, und bei Auswahl des **Wert**, klicken Sie dann **Variablentyp** gibt den geeigneten Typ für den Wert an, das Steuerelement enthalten kann. Finden Sie unter [Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md) für Weitere Informationen.  
  
     Dieser Wert hängt von der Auswahl im **Kontroll-ID** und kann nicht geändert werden.  
  
 **Variablenname**  
 Legt den Namen der Membervariable, die Sie hinzufügen. Membervariablen beginnen in der Regel mit der identifizierende Zeichenfolge "M_" die standardmäßig für Sie bereitgestellt wird.  
  
 **Steuerelementvariable**  
 Gibt an, dass die Membervariable ein Steuerelements in ein Dialogfeld mit verwaltet [Datenaustausch und datenvalidierung](../mfc/dialog-data-exchange-and-validation.md) unterstützen. Finden Sie unter [DoDataExchange](../mfc/reference/cwnd-class.md#dodataexchange) für Weitere Informationen. Diese Option steht nur für Membervariablen von abgeleiteten Klassen hinzugefügt [CDialog](../mfc/reference/cdialog-class.md). Aktivieren Sie dieses Kontrollkästchen zum Aktivieren der **Kontroll-ID** und **Steuerelementtyp** Optionen.  
  
 **Steuerelement-ID**  
 Legt die ID für die Steuerelementvariable, die Sie hinzufügen. Wählen Sie aus der Liste aus, die ID für den Typ des Steuerelements für die Sie die Membervariable hinzufügen. Die Liste ist nur aktiv, wenn die **Steuerelementvariable** aktiviert ist, und er ist begrenzt-IDs für die Steuerelemente zum Dialogfeld bereits hinzugefügt. Z. B. für den Standard **OK** Schaltfläche, um die Steuerelement-ID ist **IDOK**.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Steuerelement**|Diese Option ist standardmäßig für den Steuerelementtyp "festgelegt. Er verwaltet das Steuerelement selbst und nicht den Status oder den Inhalt (wie Sie möglicherweise mit einem Listenfeld, Kombinationsfeld oder im Bearbeitungsfeld möchten) des Steuerelements.|  
|**Wert**|Diese Option steht nur für Steuerelementtypen, die einen Wert (z. B. ein Bearbeitungsfeld) enthalten oder einen Zustand (z. B. Kontrollkästchen) wiedergeben können, und für die Sie möglicherweise verwalten, Bereich, Inhalt und Status. Finden Sie unter [Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md) für Weitere Informationen.|  
  
 **Kategorie**  
 Gibt an, ob die Variable auf einen Steuerelementtyp oder den Wert des Steuerelements basiert.  
  
 **Steuerelementtyp**  
 Legt den Typ des Steuerelements hinzugefügt werden. Dieses Feld ist nicht verfügbar ist, zu ändern. Eine Schaltfläche enthält z. B. den Steuerelementtyp " **Schaltfläche**, und ein Kombinationsfeld hat den Steuerelementtyp" **COMBOBOX**. Finden Sie unter [Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md) für Weitere Informationen.  
  
 **Maximale Anzahl von Zeichen**  
 Nur verfügbar, wenn **Variablentyp** festgelegt ist, um [CString](../atl-mfc-shared/reference/cstringt-class.md). Gibt die maximale Anzahl von Zeichen, die das Steuerelement aufnehmen kann.  
  
 **Minimalwert**  
 Nur verfügbar, wenn der Variablentyp ist **BOOL**, `int`, **"uint"**, **lange**, `DWORD`, **"float"**, **doppelte**, **BYTE**, **kurze**, [COLECurrency](../mfc/reference/colecurrency-class.md) oder [CTime](../atl-mfc-shared/reference/ctime-class.md). Gibt den niedrigsten Wert für eine Skalierung oder den Datumsbereich an.  
  
 **Max-Wert**  
 Nur verfügbar, wenn der Variablentyp ist **BOOL**, `int`, **"uint"**, **lange**, `DWORD`, **"float"**, **doppelte**, **BYTE**, **kurze**, `COLECurrency` oder `CTime`. Gibt den höchsten Wert für eine Skalierung oder den Datumsbereich an.  
  
 **.h-Datei**  
 Für ActiveX-Steuerelemente erfordern, deren Membervariablen eine Wrapperklasse. Legt den Namen der Headerdatei So fügen Sie der Klassendeklaration hinzu.  
  
 **CPP-Datei**  
 Für ActiveX-Steuerelemente erfordern, deren Membervariablen eine Wrapperklasse. Legt den Namen der Implementierungsdatei So fügen Sie der Klassendefinition hinzu.  
  
 **Kommentar**  
 Stellt einen Kommentar in der Headerdatei für die Membervariable bereit.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)