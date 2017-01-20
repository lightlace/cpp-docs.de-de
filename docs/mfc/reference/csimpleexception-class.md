---
title: "CSimpleException Class"
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
  - "CSimpleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleException class"
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist eine Basisklasse für Ressource\-wichtige MFC\-Ausnahmen.  
  
## Syntax  
  
```  
  
class AFX_NOVTABLE CSimpleException : public CException  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](../Topic/CSimpleException::CSimpleException.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](../Topic/CSimpleException::GetErrorMessage.md)|Stellt Text über einen Fehler bereit, der aufgetreten ist.|  
  
## Hinweise  
 `CSimpleException` ist die Basisklasse für Ressource\-wichtige MFC\-Ausnahmen und bearbeitet den Besitz und die Initialisierung einer Fehlermeldung.  Die folgenden Klassen verwenden `CSimpleException` als ihre Basisklasse:  
  
|||  
|-|-|  
|[CMemoryExceptions\-Klasse](../../mfc/reference/cmemoryexception-class.md)|Ausnahme aufgrund ungenügenden Arbeitsspeichers|  
|[CNotSupportedExceptions\-Klasse](../../mfc/reference/cnotsupportedexception-class.md)|Anforderung für einen nicht unterstützten Vorgang|  
|[CResourceExceptions\-Klasse](../../mfc/reference/cresourceexception-class.md)|Windows\-Ressource nicht gefunden oder nicht erstellbar|  
|[CUserExceptions\-Klasse](../../mfc/reference/cuserexception-class.md)|Ausnahme, die eine Ressource angibt, konnte nicht gefunden werden|  
|[CInvalidArgExceptions\-Klasse](../../mfc/reference/cinvalidargexception-class.md)|Ausnahme, die ein ungültiges Argument angibt|  
  
 Da `CSimpleException` eine abstrakte Basisklasse ist, können Sie ein `CSimpleException`\-Objekt nicht direkt deklarieren.  Stattdessen müssen Sie abgeleitete Objekte wie die in der vorherigen Tabelle deklarieren.  Wenn Sie eine eigene abgeleitete Klasse deklarieren, verwenden Sie die vorherigen Klassen als Modell.  
  
 Weitere Informationen finden Sie im Thema [CExceptions\-Klasse](../../mfc/reference/cexception-class.md) und [Ausnahmebehandlung \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## Anforderungen  
 **Header:** afx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Ausnahmebehandlung](../../mfc/exception-handling-in-mfc.md)