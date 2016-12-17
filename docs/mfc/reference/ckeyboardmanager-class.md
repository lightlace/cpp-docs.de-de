---
title: "CKeyboardManager Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CKeyboardManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyboardManager class"
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CKeyboardManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet Tastenkombinationstabellen für die Hauptrahmenfenster\- und Elementrahmenfenster.  
  
## Syntax  
  
```  
class CKeyboardManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Description|  
|[CKeyboardManager::CKeyboardManager](../Topic/CKeyboardManager::CKeyboardManager.md)|Erstellt ein `CKeyboardManager`\-Objekt.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Description|  
|[CKeyboardManager::CleanUp](../Topic/CKeyboardManager::CleanUp.md)|Löscht die Tastenkombinationstabellen.|  
|[CKeyboardManager::FindDefaultAccelerator](../Topic/CKeyboardManager::FindDefaultAccelerator.md)|Ruft die Standardbreite Tastenkombination für den angegebenen Befehl und das Fenster ab.|  
|[CKeyboardManager::IsKeyHandled](../Topic/CKeyboardManager::IsKeyHandled.md)|Bestimmt, ob ein Schlüssel durch die Zugriffstastentabelle behandelt wird.|  
|[CKeyboardManager::IsKeyPrintable](../Topic/CKeyboardManager::IsKeyPrintable.md)|Gibt an, ob ein druckbare Zeichen ist.|  
|[CKeyboardManager::IsShowAllAccelerators](../Topic/CKeyboardManager::IsShowAllAccelerators.md)|Gibt an, ob Menüs alle Tastenkombinationen für einen Befehl oder nur die standardmäßige Tastenkombination anzeigen.|  
|[CKeyboardManager::LoadState](../Topic/CKeyboardManager::LoadState.md)|Lädt die Tastenkombinationstabellen aus der Windows\-Registrierung.|  
|[CKeyboardManager::ResetAll](../Topic/CKeyboardManager::ResetAll.md)|Lädt die Tastenkombinationstabellen aus der Anwendungsressource erneut.|  
|[CKeyboardManager::SaveState](../Topic/CKeyboardManager::SaveState.md)|Speichert die Tastenkombinationstabellen zur Windows\-Registrierung.|  
|[CKeyboardManager::ShowAllAccelerators](../Topic/CKeyboardManager::ShowAllAccelerators.md)|Gibt an, ob das Framework alle Tastenkombinationen für alle Befehle anzeigt, oder eine einzelne Tastenkombination für jeden Befehl an.  Diese Methode hat keine Befehle, die nur eine zugeordnete Tastenkombination haben.|  
|[CKeyboardManager::TranslateCharToUpper](../Topic/CKeyboardManager::TranslateCharToUpper.md)|Konvertiert ein Zeichen zu seinem oberen Register.|  
|[CKeyboardManager::UpdateAccelTable](../Topic/CKeyboardManager::UpdateAccelTable.md)|Aktualisiert eine Tastenkombinationstabelle mit einer neuen Tastenkombinationstabelle.|  
  
## Hinweise  
 Die Member dieser Klasse ermöglichen es Ihnen, und Lasttastenkombinationstabellen zur Windows\-Registrierung zu speichern, eine Vorlage verwenden, um die Abkürzungstastentabellen zu aktualisieren, und die standardmäßige Tastenkombination für einen Befehl in einem Rahmenfenster zu suchen.  Außerdem kann das Objekt `CKeyboardManager` Sie steuern, wie Zugriffstasten dem Benutzer angezeigt werden.  
  
 Sie sollten ein `CKeyboardManager`\-Objekt nicht manuell erstellen.  Es wird automatisch vom Framework der Anwendung erstellt.  Sie sollten [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md) während des Initialisierungsprozesses der Anwendung aufrufen.  Um einen Zeiger auf den Tastaturmanager für die Anwendung abzurufen, rufen Sie [CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md) auf.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Zeiger auf einen `CKeyboardManager`\-Objekt aus einer Klasse `CWinAppEx` abgerufen und wie alle Tastenkombinationen veranschaulicht, die mit Menübefehlen zugeordnet werden.  Dieser Codeausschnitt ist Teil [Gewohnheits\-Seitenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_CustomPages#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_CustomPages#5)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## Anforderungen  
 **Header:** afxkeyboardmanager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)   
 [Anpassen von Tastatur und Maus](../../mfc/keyboard-and-mouse-customization.md)