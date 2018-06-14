---
title: Assistent zum Implementieren von Schnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.interface.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Interface Wizard [C++]
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf2ddf83b7a03f8d4e01b61f82e46e0d26a5547b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340540"
---
# <a name="implement-interface-wizard"></a>Assistent zum Implementieren von Schnittstellen
Dieser Assistent implementiert eine Schnittstelle für ein COM-Projekt. Implementierungen vieler Schnittstellen sind in den COM-Bibliotheken enthalten, die in Visual Studio und Windows verfügbar sind. Eine Schnittstellen-Implementierung wird einem Objekt zugeordnet, wenn eine Schnittstelle dieses Objekts erstellt wird. Diese stellt die Dienste bereit, die das Objekt anbietet.  
  
 Eine Erläuterung der Schnittstellen und Implementierungen finden Sie im Windows SDK unter [Interfaces and Interface Implementations (Schnittstellen und Schnittstellenimplementierungen)](http://msdn.microsoft.com/library/windows/desktop/ms694356).  
  
 **Implement interface from** (Schnittstelle implementieren aus)  
 Gibt den Speicherort der Typbibliothek an, aus der die Schnittstelle erstellt wird.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Projekt**|Die Typbibliothek ist ein Teil des Projekts.|  
|**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken werden unter **Verfügbare Typbibliotheken** aufgeführt.|  
|**Datei**|Die Typbibliothek ist nicht unbedingt im System registriert, sondern in einer Datei enthalten. Sie müssen den Dateispeicherort unter **Speicherort** angeben.|  
  
 **Verfügbare Typbibliotheken**  
 Zeigt die verfügbaren Typbibliotheken an, die die Schnittstellendefinitionen enthalten, die Sie implementieren können. Wenn Sie unter **Implement interface from** (Schnittstelle implementieren aus) auf **Datei** klicken, kann dieses Feld nicht geändert werden.  
  
 **Position**  
 Zeigt den Speicherort der Typbibliothek an, die in der Liste **Verfügbare Typbibliotheken** aktuell ausgewählt ist. Wenn Sie unter **Implement interface from** (Schnittstelle implementieren aus) auf **Datei** geklickt haben, klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um eine Datei zu suchen, die die zu verwendende Typbibliothek enthält.  
  
 **Schnittstellen**  
 Zeigt die Schnittstellen an, deren Definitionen in der aktuell im Feld **Verfügbare Typbibliotheken** ausgewählten Typbibliothek enthalten sind.  
  
> [!NOTE]
>  Schnittstellen mit dem gleichen Namen wie die, die bereits vom ausgewählten Objekt implementiert wurden, werden nicht im Feld **Schnittstellen** angezeigt.  
  
|Schaltfläche „Übertragen“|Beschreibung|  
|---------------------|-----------------|  
|**>**|Fügt den Namen der aktuell in der Liste **Schnittstellen** ausgewählten Schnittstelle der Liste **Schnittstellen implementieren** hinzu.|  
|**>>**|Fügt alle Namen der in der Liste **Schnittstellen** verfügbaren Schnittstellen der Liste **Schnittstellen implementieren** hinzu.|  
|**<**|Entfernt den Namen der Schnittstelle, die aktuell in der Liste **Schnittstellen implementieren** ausgewählt ist.|  
|**<\<**|Entfernt alle Namen der Schnittstellen, die aktuell in der Liste **Schnittstellen implementieren** aufgelistet sind.|  
  
 **Schnittstellen implementieren**  
 Zeigt die Namen der Schnittstellen an, die Sie zum Implementieren in Ihr Objekt ausgewählt haben.  
  
> [!NOTE]
>  Wenn Sie mehr als eine Schnittstelle einfügen, die von `IDispatch` abgeleitet wird, oder wenn Sie versuchen eine Schnittstelle zu implementieren, die von einer Schnittstelle abgeleitet wird, die sich bereits in der Klasse befindet, müssen Sie die COM_MAP-Einträge voneinander unterscheiden. Weitere Informationen finden Sie unter [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2).  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)