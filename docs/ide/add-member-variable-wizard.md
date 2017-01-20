---
title: "Assistent zum Hinzuf&#252;gen von Membervariablen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.variable.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistent zum Hinzufügen von Membervariablen [C++]"
ms.assetid: 73e8fa99-ac1a-42e2-8fc2-4684b9eb6d4d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Assistent zum Hinzuf&#252;gen von Membervariablen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Assistent fügt der Headerdatei eine Deklaration einer Membervariablen hinzu. Außerdem kann er der CPP\-Datei, abhängig von den ausgewählten Optionen, Code hinzufügen.  Nachdem Sie die Membervariable mit dem Assistenten hinzugefügt haben, können Sie den Code in der Entwicklungsumgebung bearbeiten.  
  
 **Zugriff**  
 Legt die Zugriffsebene für die Membervariable fest.  Zugriffsmodifizierer sind Schlüsselwörter, die festlegen, welchen Zugriff andere Klassen auf die Membervariable haben.  Weitere Informationen zum Festlegen von Zugriffsebenen finden Sie unter [Memberzugriff\-Steuerelement](../cpp/member-access-control-cpp.md).  Die Zugriffsebene für die Membervariable ist standardmäßig auf **public** gesetzt.  
  
-   [public](../cpp/public-cpp.md)  
  
-   [protected](../cpp/protected-cpp.md)  
  
-   [private](../cpp/private-cpp.md)  
  
 **Variablentyp**  
 Legt den Rückgabetyp für die hinzugefügte Membervariable fest.  
  
-   Wenn Sie eine Membervariable hinzufügen, die kein Dialogfeld\-Steuerelement ist, wählen Sie eine Variable aus der Liste der verfügbaren Typen aus.  
  
     Weitere Informationen zu den Typen finden Sie unter [Grundlegende Typen](../cpp/fundamental-types-cpp.md).  
  
    |||  
    |-|-|  
    |`char`|**short**|  
    |**double**|`unsigned char`|  
    |**float**|`unsigned int`|  
    |`int`|`unsigned long`|  
    |**long**||  
  
-   Wenn Sie eine Membervariable für ein Dialogfeld\-Steuerelement hinzufügen, wird in dieses Feld der Objekttyp eingetragen, der für ein Steuerelement oder einen Wert zurückgegeben wird.  Wenn Sie **Steuerelement** aktivieren, wird unter **Variablentyp** die Basisklasse des Steuerelements angegeben, das Sie im Feld **Steuerelement\-ID** auswählen.  Wenn das Dialogfeld\-Steuerelement einen Wert aufnehmen kann und Sie **Wert** aktivieren, wird unter **Variablentyp** der Werttyp angegeben, den das Steuerelement enthalten kann.  Weitere Informationen finden Sie unter [Dialogfeld\-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md).  
  
     Dieser Wert hängt von der Auswahl im Feld **Steuerelement\-ID** ab und kann nicht geändert werden.  
  
 **Variablenname**  
 Legt den Namen der hinzugefügten Membervariablen fest.  Membervariablen beginnen normalerweise mit der typischen Zeichenfolge "m\_,", die standardmäßig vorgegeben wird.  
  
 **Steuerelementvariable**  
 Gibt an, dass die Membervariable ein Steuerelement innerhalb eines Dialogfelds verwaltet, das [Datenaustausch und Datenvalidierung](../mfc/dialog-data-exchange-and-validation.md) unterstützt.  Weitere Informationen finden Sie unter [DoDataExchange](../Topic/CWnd::DoDataExchange.md).  Diese Option ist nur für Membervariablen verfügbar, die Klassen hinzugefügt wurden, die von [CDialog](../mfc/reference/cdialog-class.md) abgeleitet sind.  Aktivieren Sie dieses Kontrollkästchen, um die Optionen **Steuerelement\-ID** und **Steuerelementtyp** zu aktivieren.  
  
 **ID des Steuerelements**  
 Legt die ID für die Steuerelementvariable fest, die Sie hinzufügen.  Wählen Sie aus der Liste die ID für den Steuerelementtyp aus, dem Sie eine Membervariable hinzufügen.  Diese Liste ist nur aktiviert, wenn das Kontrollkästchen **Steuerelementvariable** aktiviert ist. Sie enthält nur IDs von Steuerelementen, die dem Dialogfeld bereits hinzugefügt wurden.  Die Steuerelement\-ID für die Standardschaltfläche **OK** lautet beispielsweise **IDOK**.  
  
|Option|Beschreibung|  
|------------|------------------|  
|**Steuerelement**|Diese Option ist standardmäßig für den Steuerelementtyp aktiviert.  Mit dieser Option wird das Steuerelement selbst und nicht sein Zustand oder Inhalt verwaltet \(was eher auf ein Listenfeld, ein Kombinationsfeld oder ein Eingabefeld zutrifft\).|  
|**Wert**|Diese Option ist nur für Steuerelementtypen verfügbar, die einen Wert enthalten können \(z. B. ein Eingabefeld\) oder einen Zustand wiedergeben \(z. B. ein Kontrollkästchen\) und deren Gültigkeitsbereich, Inhalt oder Zustand Sie ändern möchten.  Weitere Informationen finden Sie unter [Dialogfeld\-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md).|  
  
 **Kategorie**  
 Legt fest, ob die Variable auf dem Steuerelementtyp oder dem Wert des Steuerelements basiert.  
  
 **Steuerelementtyp**  
 Legt den Typ des Steuerelements fest, das Sie hinzufügen.  Dieses Feld kann nicht geändert werden.  Eine Schaltfläche hat beispielsweise den Steuerelementtyp **BUTTON** und ein Kombinationsfeld den Steuerelementtyp **COMBOBOX**.  Weitere Informationen finden Sie unter [Dialogfeld\-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md).  
  
 **Max. Zeichen**  
 Diese Option ist nur verfügbar, wenn **Variablentyp** auf [CString](../atl-mfc-shared/reference/cstringt-class.md) gesetzt ist.  Legt die maximale Anzahl von Zeichen fest, die das Steuerelement enthalten darf.  
  
 **Min. Wert**  
 Diese Option ist nur verfügbar, wenn der Variablentyp **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, [COLECurrency](../mfc/reference/colecurrency-class.md) oder [CTime](../atl-mfc-shared/reference/ctime-class.md) lautet.  Gibt den niedrigsten Wert an, der für eine Skala oder einen Datumsbereich zulässig ist.  
  
 **Max. Wert**  
 Diese Option ist nur verfügbar, wenn der Variablentyp **BOOL**, `int`, **UINT**, **long**, `DWORD`, **float**, **double**, **BYTE**, **short**, `COLECurrency` oder `CTime` lautet.  Gibt den höchsten Wert an, der für eine Skala oder einen Datumsbereich zulässig ist.  
  
 **.h\-Datei**  
 Für ActiveX\-Steuerelemente, deren Membervariablen eine Wrapperklasse erfordern.  Legt den Namen der Headerdatei fest, der die Klassendeklaration hinzugefügt werden soll.  
  
 **.cpp\-Datei**  
 Für ActiveX\-Steuerelemente, deren Membervariablen eine Wrapperklasse erfordern.  Legt den Namen der Implementierungsdatei fest, der die Klassendefinition hinzugefügt werden soll.  
  
 **Kommentar**  
 Fügt einen Kommentar für die Membervariable in die Headerdatei ein.  
  
## Siehe auch  
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)