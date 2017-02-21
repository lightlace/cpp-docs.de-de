---
title: "CPathT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPathT"
  - "CPathT"
  - "ATL::CPathT<StringType>"
  - "ATL::CPathT"
  - "ATL.CPathT<StringType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPathT class"
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CPathT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt einen Pfad dar.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template< typename   
      StringType  
      >   
class CPathT  
```  
  
#### Parameter  
 `StringType`  
 Die für den Pfad zu verwenden, ATL\-\/MFCzeichenfolgenklasse \(siehe [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)\).  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CPathT::PCXSTR](../Topic/CPathT::PCXSTR.md)|Ein konstanter Zeichenfolgentyp.|  
|[CPathT::PXSTR](../Topic/CPathT::PXSTR.md)|Ein Zeichenfolgentyp.|  
|[CPathT::XCHAR](../Topic/CPathT::XCHAR.md)|Ein Zeichentyp.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPathT::CPathT](../Topic/CPathT::CPathT.md)|Der Konstruktor für den Pfad.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPathT::AddBackslash](../Topic/CPathT::AddBackslash.md)|Rufen Sie diese Methode auf, um einen umgekehrten Schrägstrich am Ende einer Zeichenfolge hinzuzufügen, um die richtige Syntax für einen Pfad zu erstellen.|  
|[CPathT::AddExtension](../Topic/CPathT::AddExtension.md)|Rufen Sie diese Methode auf, um eine Dateierweiterung einem Pfad hinzuzufügen.|  
|[CPathT::Append](../Topic/CPathT::Append.md)|Rufen Sie diese Methode auf, um eine Zeichenfolge zum aktuellen Pfad anzufügen.|  
|[CPathT::BuildRoot](../Topic/CPathT::BuildRoot.md)|Rufen Sie diese Methode auf, um einen Stammpfad aus einer angegebenen Laufwerknummer zu erstellen.|  
|[CPathT::Canonicalize](../Topic/CPathT::Canonicalize.md)|Rufen Sie diese Methode auf, um den Pfad zur kanonischen Form zu konvertieren.|  
|[CPathT::Combine](../Topic/CPathT::Combine.md)|Rufen Sie diese Methode auf, um eine Zeichenfolge, die einen Verzeichnisnamen darstellen und eine Zeichenfolge verketten, die einen Dateipfadnamen in einen Pfad darstellt.|  
|[CPathT::CommonPrefix](../Topic/CPathT::CommonPrefix.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob der angegebene Pfad ein Präfix mit dem aktuellen Pfad freigibt.|  
|[CPathT::CompactPath](../Topic/CPathT::CompactPath.md)|Rufen Sie diese Methode auf, um einen Dateipfad abgeschnitten werden, um innerhalb einer angegebenen Pixelbreite anpassen, indem Sie Pfadkomponenten mit Auslassungszeichen ersetzen.|  
|[CPathT::CompactPathEx](../Topic/CPathT::CompactPathEx.md)|Rufen Sie diese Methode auf, um einen Dateipfad abgeschnitten werden, um innerhalb einer angegebenen Anzahl von Zeichen an, indem Sie Pfadkomponenten mit Auslassungszeichen ersetzen.|  
|[CPathT::FileExists](../Topic/CPathT::FileExists.md)|Rufen Sie diese Methode auf, um sicherzustellen, dass die Datei an diesem Pfadnamen vorhanden ist.|  
|[CPathT::FindExtension](../Topic/CPathT::FindExtension.md)|Rufen Sie diese Methode auf, um die Position der Dateierweiterung innerhalb des Pfads zu suchen.|  
|[CPathT::FindFileName](../Topic/CPathT::FindFileName.md)|Rufen Sie diese Methode auf, um die Position des Dateinamens innerhalb des Pfads zu suchen.|  
|[CPathT::GetDriveNumber](../Topic/CPathT::GetDriveNumber.md)|Rufen Sie diese Methode auf, um den Pfad für einen Laufwerkbuchstaben innerhalb des Bereichs von "A" in "Z" zu suchen und die entsprechende Laufwerknummer zurückzugeben.|  
|[CPathT::GetExtension](../Topic/CPathT::GetExtension.md)|Rufen Sie diese Methode auf, um die Dateierweiterung vom Pfad abzurufen.|  
|[CPathT::IsDirectory](../Topic/CPathT::IsDirectory.md)|Rufen Sie diese Methode auf, um sicherzustellen, dass der Pfad ein gültiges Verzeichnis befindet.|  
|[CPathT::IsFileSpec](../Topic/CPathT::IsFileSpec.md)|Rufen Sie diese Methode auf, um einen Pfad für alle Pfad\-Abgrenzungszeichen zu suchen, \(beispielsweise ": " oder "\\ "\).  Wenn es gibt, stellen sich keine Pfad\-Abgrenzungszeichen, der Pfad berücksichtigt wird ein als Datei\-Spezifikationspfad dar.|  
|[CPathT::IsPrefix](../Topic/CPathT::IsPrefix.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob ein Pfad ein gültiges Präfix des Typs enthält, der vom `pszPrefix` übergeben wird.|  
|[CPathT::IsRelative](../Topic/CPathT::IsRelative.md)|Rufen Sie diese Methode auf, um zu bestimmen, wenn der Pfad relativ ist.|  
|[CPathT::IsRoot](../Topic/CPathT::IsRoot.md)|Rufen Sie diese Methode auf, um zu ermitteln, ob der Pfad ein Verzeichnisstamm ist.|  
|[CPathT::IsSameRoot](../Topic/CPathT::IsSameRoot.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob ein anderer Pfad eine Komponente des allgemeinen Stamms mit dem aktuellen Pfad verfügt.|  
|[CPathT::IsUNC](../Topic/CPathT::IsUNC.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob der Pfad ein gültiger Pfad UNC \(Universal Naming Convention\) für einen Server und eine Freigabe ist.|  
|[CPathT::IsUNCServer](../Topic/CPathT::IsUNCServer.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob der Pfad ein gültiger Pfad UNC \(Universal Naming Convention\) für einen Server ist.|  
|[CPathT::IsUNCServerShare](../Topic/CPathT::IsUNCServerShare.md)|Rufen Sie diese Methode auf, um, dass der Pfad ein gültiger Freigabenpfad UNC \(Universal Naming Convention\) ist, \\\\*Server*\\*Freigabe* zu bestimmen.|  
|[CPathT::MakePretty](../Topic/CPathT::MakePretty.md)|Rufen Sie diese Methode auf, um einen Pfad zu allen umwandeln können, um dem Pfad eine einheitliche Darstellung zu geben.|  
|[CPathT::MatchSpec](../Topic/CPathT::MatchSpec.md)|Rufen Sie diese Methode auf, um den Pfad für eine Zeichenfolge suchen, die einen Platzhalterabgleichungstyp enthält.|  
|[CPathT::QuoteSpaces](../Topic/CPathT::QuoteSpaces.md)|Rufen Sie diese Methode auf, um den Pfad in Anführungszeichen setzen, wenn er einem Leerzeichen enthält.|  
|[CPathT::RelativePathTo](../Topic/CPathT::RelativePathTo.md)|Rufen Sie diese Methode auf, um einen relativen Pfad aus einer Datei oder der Ordner zu anderen zu erstellen.|  
|[CPathT::RemoveArgs](../Topic/CPathT::RemoveArgs.md)|Rufen Sie diese Methode auf, um alle Befehlszeilenargumente vom Pfad zu entfernen.|  
|[CPathT::RemoveBackslash](../Topic/CPathT::RemoveBackslash.md)|Rufen Sie diese Methode auf, um den nachgestellten umgekehrten Schrägstrich vom Pfad zu entfernen.|  
|[CPathT::RemoveBlanks](../Topic/CPathT::RemoveBlanks.md)|Rufen Sie diese Methode auf, um alle führenden und nachgestellten Leerzeichen im Pfad zu entfernen.|  
|[CPathT::RemoveExtension](../Topic/CPathT::RemoveExtension.md)|Rufen Sie diese Methode auf, um die Dateierweiterung vom Pfad zu entfernen, sofern vorhanden.|  
|[CPathT::RemoveFileSpec](../Topic/CPathT::RemoveFileSpec.md)|Rufen Sie diese Methode auf, um den Dateinamen und den nachgestellten umgekehrten Schrägstrich vom Pfad zu entfernen, wenn sie verfügt.|  
|[CPathT::RenameExtension](../Topic/CPathT::RenameExtension.md)|Rufen Sie diese Methode auf, um die Dateinamenerweiterung im Pfad durch eine neue Erweiterung zu ersetzen.  Wenn der Dateiname keine Erweiterung enthält, wird die Erweiterung an das Ende der Zeichenfolge angehängt.|  
|[CPathT::SkipRoot](../Topic/CPathT::SkipRoot.md)|Rufen Sie diese Methode auf, um einen Pfad zu analysieren und den Laufwerkbuchstaben oder UNC\-Server\/Freigabe Pfadteil ignorieren.|  
|[CPathT::StripPath](../Topic/CPathT::StripPath.md)|Rufen Sie diese Methode auf, um den Pfadteil einen vollqualifizierten Pfad und Dateinamen des zu entfernen.|  
|[CPathT::StripToRoot](../Topic/CPathT::StripToRoot.md)|Rufen Sie diese Methode auf, um alle Teile des Pfads mit Ausnahme der Stamminformationen zu entfernen.|  
|[CPathT::UnquoteSpaces](../Topic/CPathT::UnquoteSpaces.md)|Rufen Sie diese Methode auf, um Anführungszeichen und Ende eines Pfades von Anfang an zu entfernen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPathT::operator const StringType &](../Topic/CPathT::operator%20const%20StringType%20&.md)|Dieser Operator ermöglicht das wie eine Zeichenfolge behandelt werden Objekt.|  
|[CPathT::operator CPathT::PCXSTR](../Topic/CPathT::operator%20CPathT::PCXSTR.md)|Dieser Operator ermöglicht das wie eine Zeichenfolge behandelt werden Objekt.|  
|[CPathT::operator StringType &](../Topic/CPathT::operator%20StringType%20&.md)|Dieser Operator ermöglicht das wie eine Zeichenfolge behandelt werden Objekt.|  
|[CPathT::operator \+\=](../Topic/CPathT::operator%20+=.md)|Dieser Operator wird eine Zeichenfolge zum Pfad.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPathT::m\_strPath](../Topic/CPathT::m_strPath.md)|Der Pfad.|  
  
## Hinweise  
 `CPath`, `CPathA` und `CPathW` sind Instanziierungen von `CPathT` definierten, wie folgt:  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## Anforderungen  
 **Header:** atlpath.h  
  
## Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)