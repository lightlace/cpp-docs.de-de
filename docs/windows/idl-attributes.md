---
title: "IDL Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], reference topics"
  - "IDL attributes"
  - ".idl files, attributes"
  - "IDL files, attributes"
  - ".idl files"
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDL Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Herkömmlicherweise eine IDL\-Datei bedeutete zu warten, dass Sie mussten:  
  
-   Stellen Sie mit der Struktur und die Syntax einer IDL\-Datei vertraut, in der Lage zu sein, sie zu ändern.  
  
-   Erstellen Sie einen Assistenten, mit dem Sie einige Aspekte der IDL\-Datei würde ändern können.  
  
 Nun können Sie die IDL\-Datei aus einer Quellcodedatei mithilfe von Attributen von Visual C\+\+ IDL ändern.  In vielen Fällen verfügen über Attribute von Visual C\+\+ IDL den gleichen Namen wie MIDL\-Attribute.  Wenn der Name eines Attributs von Visual C\+\+ IDL\-Datei und ein MIDL\-Attribut identisch sind, bedeutet dies, dass das das Visual C\+\+\-Attributs Sie die Quellcodedatei in eine IDL\-Datei ergibt, die ihr Namensvetter MIDL\-Attribut enthält.  Allerdings kann ein Attribut von Visual C\+\+ nicht IDL die gesamte Funktionalität eines MIDL\-Attributs bereit.  
  
 Ein nicht mit [COM\-Attribute](../windows/com-attributes.md)IDL\-Attribute, können Sie Schnittstellen definieren.  Wenn der Quellcode kompiliert wird, werden die Attribute, mit denen die generierten IDL\-Datei definiert.  Wenn sie mit COM\-Attributen in einem ATL\-Projekt verwendet werden, führen einige IDL\-Attribute, wie **coclass**, Code in das Projekt eingefügt werden soll.  
  
 Beachten Sie, dass [idl\_quote](../windows/idl-quote.md) Sie MIDL\-Konstrukte verwenden können, die nicht in die aktuelle Version von Visual C\+\+ unterstützt werden.  Dieses und andere Attribute wie [importlib](../windows/importlib.md) und [includelib](../windows/includelib-cpp.md) können Sie vorhandene IDL\-Dateien im aktuellen Visual C\+\+\-Projekts verwendet werden soll.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[aggregierbar](../windows/aggregatable.md)|Gibt an, dass ein Steuerelement durch ein anderes Steuerelement aggregiert werden kann.|  
|[appobject](../windows/appobject.md)|Identifiziert die Co\-Klasse als Anwendungsobjekt, das einer vollständigen EXE\-Anwendung zugeordnet ist, und gibt an, dass Features und Eigenschaften der Co\-Klasse in dieser Typbibliothek global verfügbar sind.|  
|[async\_uuid](../windows/async-uuid.md)|Gibt das UUID an, das den MIDL\-Compiler, weist die synchronen und asynchronen Versionen einer COM\-Schnittstelle zu definieren.|  
|[bindable](../windows/bindable.md)|Gibt an, dass die Eigenschaft Datenbindungen unterstützt.|  
|[call\_as](../windows/call-as.md)|Aktiviert eine Funktion nicht remotefähig zu einer Remotewebsite Funktion zugeordnet werden soll.|  
|[case](../windows/case-cpp.md)|Wird mit dem [switch\_type](../windows/switch-type.md)\-Attribut in einer Union.|  
|[Co\-Klasse](../windows/coclass.md)|Platziert Klassendefinition in eine IDL\-Datei als Co\-Klasse.|  
|[\-Steuerelement](../windows/control.md)|Gibt an, dass der benutzerdefinierte Typ ein Steuerelement befindet.|  
|[cpp\_quote](../windows/cpp-quote.md)|Gibt die angegebene Zeichenfolge in Anführungszeichen, ohne dass die generierte Headerdatei ab.|  
|[defaultbind](../windows/defaultbind.md)|Gibt die einzige bindbare Eigenschaft an, die das Objekt am besten darstellt.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Wird für Visual Basic\-Code\-Optimierung.|  
|[defaultvalue](../windows/defaultvalue.md)|Ermöglicht die Angabe eines Standardwerts einen typisierten optionalen Parameter zu.|  
|[default](../windows/default-cpp.md)|Gibt an, dass die benutzerdefinierte oder die Dispatchschnittstelle, die innerhalb einer Co\-Klasse definierten Programmierung der Schnittstelle darstellt.|  
|[defaultvtable](../windows/defaultvtable.md)|Definiert eine Schnittstelle als die standardmäßige vtable Schnittstelle für ein Steuerelement.|  
|[dispinterface](../windows/dispinterface.md)|Platziert eine Schnittstelle in der IDL\-Datei als Dispatchschnittstelle.|  
|[displaybind](../windows/displaybind.md)|Gibt eine Eigenschaft an, die dem Benutzer angezeigt werden sollte, als bindbar gesucht werden sollen.|  
|[dual](../windows/dual.md)|Platziert eine Schnittstelle in der IDL\-Datei als duale Schnittstelle.|  
|[Eingabe](../windows/entry.md)|Gibt eine exportierte Funktion oder einer Konstanten in einem Modul indem die Bestimmung des Einstiegspunktes in der DLL an.|  
|[first\_is](../windows/first-is.md)|Gibt den Index des ersten zu sendenden Arrayelements an.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext\-ID an, die der Benutzer Informationen über dieses Element in der Hilfedatei können.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek fest.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in einem .hlp oder CHM\-Datei an.|  
|[helpstringdll](../windows/helpstringdll.md)|Gibt den Namen der DLL an, der verwendet wird, um Zeichenfolgen Dokumente Lokalisierung \(Discovery\) auszuführen.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge an, durch die das zugehörige Element beschrieben wird.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, in einem benutzerorientierten Browser jedoch nicht angezeigt werden sollte.|  
|[idl\_module](../windows/idl-module.md)|Gibt einen Einstiegspunkt in einer DLL an.|  
|[idl\_quote](../windows/idl-quote.md)|Ermöglicht attributen verwenden oder TO IDL\-Konstrukten, die nicht in die aktuelle Version von Visual C\+\+ unterstützt werden.|  
|[id](../windows/id.md)|Gibt ein DISPID für eine Memberfunktion an \(entweder eine Eigenschaft oder eine Methode in einer Schnittstelle bzw. Dispatchschnittstelle\).|  
|[iid\_is](../windows/iid-is.md)|Gibt die IID der COM\-Schnittstelle, die auf einen Schnittstellenzeiger dargestellt wird.|  
|[immediatebind](../windows/immediatebind.md)|Gibt an, dass die Datenbank sofort alle Änderungen einer Eigenschaft eines datengebundenen Objekts benachrichtigt wird.|  
|[importlib](../windows/importlib.md)|Macht Typen, die bereits auf eine andere Typbibliothek kompiliert wurden, die der Typbibliothek verfügbar ist, die erstellt wird.|  
|[import](../windows/import.md)|Gibt ein weiteres .idl, .odl oder Headerdatei, die Definitionen enthält, die Sie aus der IDL\-Datei verweisen möchten.|  
|[Einschließen](../windows/include-cpp.md)|Gibt eine oder mehrere in der generierten IDL\-Datei Headerdateien eingefügt werden soll.|  
|[includelib](../windows/includelib-cpp.md)|Bewirkt, dass ein in der generierten IDL\-Datei oder H\-Datei .idl eingeschlossen werden soll.|  
|[in](../windows/in-cpp.md)|Gibt an, dass ein Parameter aus der aufgerufenen Prozedur an die aufrufende Prozedur übergeben werden soll.|  
|[last\_is](../windows/last-is.md)|Gibt den Index des letzten gesendet werden sollen, Arrayelements an.|  
|[lcid](../windows/lcid.md)|Ermöglicht es Ihnen, einen Gebietsschemabezeichner an eine Funktion übergeben.|  
|[length\_is](../windows/length-is.md)|Gibt die Anzahl der zu sendenden auf Arrayelemente.|  
|[lizenziert](../windows/licensed.md)|Gibt an, dass die Co\-Klasse, auf die es angewendet wird, lizenziert ist, und muss mithilfe **IClassFactory2**instanziiert werden.|  
|[local](../windows/local-cpp.md)|Ermöglicht es Ihnen, den MIDL\-Compiler als Header Steuerelement\-Generator verwenden, wenn Sie im Header des Schnittstellen verwendet werden.  Wenn in einer einzelnen Funktion verwendet werden, legt eine lokale Prozedur fest, für die keine Stubs generiert werden.|  
|[max\_is](../windows/max-is.md)|Legt den Höchstwert für einen gültigen Arrayindex.|  
|[Modul](../windows/module-cpp.md)|Definiert den Library\-Block in der IDL\-Datei.|  
|[ms\_union](../windows/ms-union.md)|Steuert die Ausrichtung der Netzwerk Informationsdarstellung von nonencapsulated Unions.|  
|[no\_injected\_text](../windows/no-injected-text.md)|Verhindert, dass der Compiler Code aufgrund der Attributverwendung einfügt.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.|  
|[nicht erstellbar](../windows/noncreatable.md)|Definiert ein Objekt, das nicht allein instanziiert werden kann.|  
|[nicht erweiterbar](../windows/nonextensible.md)|Gibt an, dass die `IDispatch` nur die Implementierung der Eigenschaften und Methoden enthält, die in der Beschreibung der aufgelisteten Schnittstellen und nicht mit zusätzlichen Member zur Laufzeit erweitert werden kann.|  
|[object](../windows/object-cpp.md)|Identifiziert eine benutzerdefinierte Schnittstelle. synonym mit benutzerdefiniertem Attribut.|  
|[odl](../windows/odl.md)|Identifiziert eine Schnittstelle während eine Schnittstelle der Objektbeschreibungssprache \(ODL\).|  
|[oleautomation](../windows/oleautomation.md)|Gibt an, dass eine Schnittstelle mit Automatisierung kompatibel ist.|  
|[optional](../windows/optional-cpp.md)|Gibt einen optionalen Parameter für eine Memberfunktion auf.|  
|[out](../windows/out-cpp.md)|Identifiziert Zeigerparameter, die von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben wird \(vom Server an den Client\).|  
|[pointer\_default](../windows/pointer-default.md)|Gibt die Standardzeiger Attribut für alle Zeiger für Zeiger mit Ausnahme der obersten Ebene angezeigt, die in den Parameterlisten enthalten sein.|  
|[Pragma](../windows/pragma.md)|Gibt die angegebene Zeichenfolge in Anführungszeichen, ohne dass die generierten IDL\-Datei ab.|  
|[ProgID](../windows/progid.md)|Gibt die ProgID für ein COM\-Objekt an.|  
|[propget](../windows/propget.md)|Gibt ein Feature von Eigenschaftenaccessors \(rufen Sie ab\) an.|  
|[propputref](../windows/propputref.md)|Gibt eine property\-setting\-Funktion an, die einen Verweis anstelle eines Werts verwendet wird.|  
|[propput](../windows/propput.md)|Gibt eine property\-setting\-Funktion an.|  
|[PTR](../windows/ptr.md)|Legt einen Zeiger als vollständiger Zeiger fest.|  
|[public](../windows/public-cpp-attributes.md)|Stellt sicher, dass eine Typdefinition in die Typbibliothek wechselt, selbst wenn sie nicht innerhalb der IDL\-Datei verwiesen wird.|  
|[Bereich](../windows/range-cpp.md)|Gibt einen Bereich der zulässigen Werten für seine Argumente oder Felder, deren Werte zur Laufzeit festgelegt sind.|  
|[readonly](../windows/readonly-cpp.md)|Verhindert Zuweisung zu einer Variablen.|  
|[ref](../windows/ref-cpp.md)|Identifiziert einen Verweiszeiger.|  
|[requestedit](../windows/requestedit.md)|Gibt an, dass die Eigenschaft die Benachrichtigung **OnRequestEdit** unterstützt.|  
|[restricted](../windows/restricted.md)|Gibt an, dass eine Bibliothek oder Member eines Moduls, Schnittstellen\- oder Dispatchschnittstelle nicht willkürlich aufgerufen werden können.|  
|[retval](../windows/retval.md)|Legt den Parameter ab, der den Rückgabewert des Members erhält.|  
|[size\_is](../windows/size-is.md)|Gibt die Größe des zugeordneten Speichers für sortierte Zeiger, sortierte Zeiger auf sortierten Zeigern und einzel\- oder mehrdimensionalen Felder an.|  
|[source](../windows/source-cpp.md)|Gibt an, dass ein Member einer Klasse, einer Eigenschaft oder Methode eine Ereignisquelle ist.|  
|[string](../windows/string-cpp.md)|Gibt an, dass eindimensionale `char`, `wchar_t`, **Byte**oder das entsprechende Array oder Zeiger zu einem solchen Array wie eine Zeichenfolge behandelt werden müssen.|  
|[switch\_is](../windows/switch-is.md)|Gibt den Ausdruck oder den Bezeichner an, die als diskriminierende Union fungiert, die das Gewerkschaftsmitglied auswählt.|  
|[switch\_type](../windows/switch-type.md)|Gibt den Typ der Variablen, die als diskriminierende Union verwendet wird.|  
|[transmit\_as](../windows/transmit-as.md)|Weist den Compiler an, um einen dargestellten Typ, den Client\- und Serveranwendungen bearbeiten, mit dem bereitgestellten Typ zuzuordnen.|  
|[uidefault](../windows/uidefault.md)|Gibt an, dass der Member Typinformationens der Standardmember für die Anzeige in der Benutzeroberfläche ist.|  
|[eindeutig](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger an.|  
|[usesgetlasterror](../windows/usesgetlasterror.md)|Erklärt den Aufrufer, dass bei einem Fehler auftreten, wenn diese Funktion `GetLastError` , der Aufrufer kann dann aufgerufen werden, um den Fehlercode abzurufen aufruft.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder eine Schnittstelle an.|  
|[v1\_enum](../windows/v1-enum.md)|Verweist auf, denen der angegebene 32\-Bit\-Entität als Aufzählungstyp gesendet wird, und nicht mit dem 16\-Bit\-Standard.|  
|[vararg](../windows/vararg.md)|Gibt an, dass die Funktion eine variable Anzahl von Argumenten akzeptieren.|  
|[vi\_progid](../windows/vi-progid.md)|Gibt ein versionsunabhängiges ProgID des Formulars an.|  
|[wire\_marshal](../windows/wire-marshal.md)|Gibt einen Datentyp an, der für die Übertragung anstelle eines anwendungsspezifischen Datentyps verwendet wird.|  
  
## Siehe auch  
 [Attributes by Group](../windows/attributes-by-group.md)   
 [Attribute Limitations](assetId:///6e6c4329-f667-4869-b991-cbe9cb7a8f61)