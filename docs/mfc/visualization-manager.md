---
title: "Visualisierungs-Manager"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Visualisierungs-Manager"
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Visualisierungs-Manager
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der visuelle Manager ist ein Objekt, das die Darstellung einer vollständigen Anwendung gesteuert.  Es fungiert als eine einzelne Klasse, in der Sie den ganzen den Zeichnungscode die Anwendung einfügen können.  Die MFC\-Bibliothek enthält mehrere visuelle manager ein.  Sie können einen eigenen visuellen Manager auch erstellen, wenn Sie eine benutzerdefinierte Ansicht für die Anwendung erstellen möchten.  Die folgenden Abbildungen zeigen die gleiche Anwendung, wenn unterschiedliche visuelle Manager ermöglicht werden:  
  
 ![Mit CMFCVisualManagerWindows gerenderte MyApp](../mfc/media/vmwindows.png "VMWindows")  
MyApp, das den CMFCVisualManagerWindows\-Sichtbarmachungsmanager verwendet  
  
 ![Mit CMFCVisualManagerVS2005 gerenderte MyApp](../mfc/media/vmvs2005.png "VMVS2005")  
MyApp, das den Manager der visuellen CMFCVisualManagerVS2005 verwendet  
  
 ![Mit CMFCVisualManagerOfficeXP gerenderte MyApp](../mfc/media/vmofficexp.png "VMOfficeXP")  
MyApp, das den CMFCVisualManagerOfficeXP\-Sichtbarmachungsmanager verwendet  
  
 ![Mit CMFCVisualManagerOffice2003 gerenderte MyApp](../mfc/media/vmoffice2003.png "VMOffice2003")  
MyApp, das den Manager der visuellen CMFCVisualManagerOffice2003 verwendet  
  
 ![Mit CMFCVisualManagerOffice2007 gerenderte MyApp](../mfc/media/msoffice2007.png "MSOffice2007")  
MyApp, das den Manager der visuellen CMFCVisualManagerOffice2007 verwendet  
  
 Standardmäßig wird der visuelle Manager den Zeichencode für einige GUI\-Elemente bei.  Um benutzerdefinierte Benutzeroberflächenelemente bereitstellen, müssen Sie die zugehörigen Zeichenmethoden des visuellen Manager überschreiben.  Eine Liste dieser Methoden, finden Sie unter [CMFCVisualManager Class](../mfc/reference/cmfcvisualmanager-class.md).  Die Methoden, die Sie überschreiben können, um eine benutzerdefinierte Darstellung bereitzustellen, sind alle Methoden, die mit `OnDraw` beginnen.  
  
 Die Anwendung kann nur ein `CMFCVisualManager`\-Objekt verfügen.  Um einen Zeiger für den visuellen Manager für die Anwendung abzurufen, rufen Sie die statische [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)\- Funktion auf.  Da alle Sichtbarmachungsmanager von `CMFCVisualManager` erben, ruft die `CMFCVisualManager::GetInstance`\-Methode einen Zeiger an den entsprechenden optischen Manager, wenn Sie einen benutzerdefinierten visuellen Manager erstellen.  
  
 Wenn Sie einen benutzerdefinierten visuellen Manager erstellen möchten, müssen Sie sie von einem visuellen Manager berechnen, der bereits vorhanden ist.  Die Standardklasse aus, um zu berechnen ist `CMFCVisualManager`.  Sie können einen anderen visuellen Manager verwenden, wenn sie besser ähnelt, was Sie für die Anwendung verwenden möchten.  Wenn Sie den visuellen Manager `CMFCVisualManagerOffice2007` verwenden möchten, aber je nur ändern, wie Trennzeichen betrachten, können Sie die benutzerdefinierte Klasse von `CMFCVisualManagerOffice2007` ableiten.  In diesem Szenario können Sie nur die Methoden zum Zeichnen von Trennzeichen überschreiben.  
  
 Es gibt zwei mögliche Möglichkeiten, einen spezifischen visuellen Manager für die Anwendung verwenden.  Eine Möglichkeit ist, die Methode [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md) aufzurufen und den entsprechenden optischen Manager als Parameter übergeben.  Das folgende Codebeispiel zeigt, wie Sie den visuellen Manager `CMFCVisualManagerVS2005` mit dieser Methode verwenden:  
  
```  
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));  
```  
  
 Die andere Möglichkeit, einen visuellen Manager in der Anwendung zu verwenden, besteht sie manuell zu erstellen.  Die Anwendung verwendet anschließend diesen neuen visuellen Manager für das gesamte Rendering.  Da nur ein `CMFCVisualManager`\-Objekt pro Anwendung geben kann, müssen Sie den aktuellen visuellen Manager löschen, bevor Sie eine neue erstellen.  Im folgenden Beispiel ist ein benutzerdefinierter `CMyVisualManager` visueller Manager, der von `CMFCVisualManager` abgeleitet wird.  Die folgende Methode ändert, welcher visuelle Manager verwendet wird, um die Anwendung anzuzeigen, abhängig von einem Index:  
  
```  
void CMyApp::SetSkin (int index)  
{  
   if (CMFCVisualManager::GetInstance() != NULL)  
   {  
      delete CMFCVisualManager::GetInstance();  
   }  
  
   switch (index)  
   {  
   case DEFAULT_STYLE:  
      // The following statement creates a new CMFCVisualManager  
      CMFCVisualManager::GetInstance();  
      break;  
  
   case CUSTOM_STYLE:  
      new CMyVisualManager;  
      break;  
  
   default:  
      CMFCVisualManager::GetInstance();  
      break;  
   }  
  
   CMFCVisualManager::GetInstance()->RedrawAll();  
}  
```  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [CMFCVisualManager Class](../mfc/reference/cmfcvisualmanager-class.md)