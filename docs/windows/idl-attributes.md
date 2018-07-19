---
title: IDL-Attribute | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- IDL attributes
- .idl files, attributes
- IDL files, attributes
- .idl files
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c522c039a0471240ba319561485e8cc7f348aaa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881548"
---
# <a name="idl-attributes"></a>IDL-Attribute
Bisher musste eine IDL-Datei verwalten mussten um:  
  
-   Mit der Struktur und Syntax einer IDL-Datei in die Lage, diese zu ändern, vertraut sein.  
  
-   Hängen Sie einen Assistenten, mit der Sie einige Aspekte der IDL-Datei ändern kann.  
  
 Jetzt können Sie die IDL-Datei in einer Quellcodedatei, die mit Visual C++-IDL-Attribute ändern. In vielen Fällen haben Visual C++-IDL-Attribute den gleichen Namen wie "MIDL" Attribute auf. Wenn Sie der Namen des Visual C++-IDL-Attribut und eine MIDL-Attribut identisch sind, bedeutet dies, dass es sich bei platzieren das Visual C++-Attribut in der Quellcodedatei in eine IDL-Datei führt, die die gleichnamige MIDL-Attribut enthält. Ein Visual C++-IDL-Attribut kann jedoch nicht alle Funktionen der MIDL-Attribut bereitstellen.  
  
 Bei Verwendung nicht mit [COM-Attribute](../windows/com-attributes.md), IDL-Attribute können Sie die Schnittstellen definieren. Wenn der Quellcode kompiliert wird, werden die Attribute zum Definieren der generierten IDL-Datei verwendet. Bei Verwendung mit COM-Attribute in einem ATL-Projekt einige IDL-Attribute, z. B. **Coclass**, dazu, dass Code in das Projekt eingefügt werden.  
  
 Beachten Sie, dass [Idl_quote](../windows/idl-quote.md) ermöglicht, die Sie verwenden, dass MIDL-Konstrukte, die nicht in der aktuellen Version von Visual C++ unterstützt werden. Diese und andere Attribute wie z. B. [Importlib](../windows/importlib.md) und [Includelib](../windows/includelib-cpp.md) Ihnen dabei helfen, die vorhandenen IDL-Dateien in Ihrem aktuellen Visual C++-Projekt verwenden.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|[Aggregierbar](../windows/aggregatable.md)|Gibt an, dass ein Steuerelement durch ein anderes Steuerelement aggregiert werden kann.|  
|[appobject](../windows/appobject.md)|Identifiziert die Co-Klasse als ein Anwendungsobjekt, die mit einer vollständigen EXE-Anwendung verknüpft ist, und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diese Typbibliothek global verfügbar sind.|  
|[async_uuid](../windows/async-uuid.md)|Gibt an, die synchrone und asynchrone Versionen einer COM-Schnittstelle definiert die MIDL-Compiler anweist, UUID.|  
|[bindable](../windows/bindable.md)|Gibt an, dass die Eigenschaft die Datenbindung unterstützt.|  
|[call_as](../windows/call-as.md)|Ermöglicht es einer nicht remotefähig-Funktion, um eine remote-Funktion zugeordnet werden.|  
|[case](../windows/case-cpp.md)|Verwendet die [Switch_type](../windows/switch-type.md) Attribut in einer Union.|  
|[coclass](../windows/coclass.md)|Stellen Klassendefinition in einer IDL-Datei als Co-Klasse.|  
|[Steuerelement](../windows/control.md)|Gibt an, dass der benutzerdefinierte Datentyp eines Steuerelements.|  
|[cpp_quote](../windows/cpp-quote.md)|Gibt die angegebene Zeichenfolge, ohne die Anführungszeichen in der Headerdatei.|  
|[defaultbind](../windows/defaultbind.md)|Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Zur Optimierung der Visual Basic-Code verwendet.|  
|[defaultvalue](../windows/defaultvalue.md)|Ermöglicht die Festlegung eines standardmäßigen Werts für einen typisierten optionale Parameter.|  
|[default](../windows/default-cpp.md)|Gibt an, dass die benutzerdefinierte Schnittstelle oder Disp-Schnittstelle innerhalb einer Co-Klasse die Standard-Programmierschnittstelle darstellt.|  
|[defaultvtable](../windows/defaultvtable.md)|Definiert eine Schnittstelle als die Vtable Standardschnittstelle für ein Steuerelement an.|  
|[dispinterface](../windows/dispinterface.md)|Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.|  
|[displaybind](../windows/displaybind.md)|Gibt eine Eigenschaft, die für den Benutzer als bindbar angezeigt werden sollen.|  
|[dual](../windows/dual.md)|Fügt eine Schnittstelle in der IDL-Datei als eine duale Schnittstelle.|  
|[entry](../windows/entry.md)|Gibt eine exportierte Funktion oder Konstante in einem Modul durch identifizieren den Einstiegspunkt in der DLL an.|  
|[first_is](../windows/first-is.md)|Gibt den Index des ersten Arrayelements übermittelt werden sollen.|  
|[helpcontext](../windows/helpcontext.md)|Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der Hilfedatei.|  
|[helpfile](../windows/helpfile.md)|Legt den Namen der Hilfedatei für eine Typbibliothek.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Gibt die ID des Hilfethemas in einer HLP oder CHM-Datei an.|  
|[helpstringdll](../windows/helpstringdll.md)|Gibt den Namen der DLL zu verwenden, um das Dokument Zeichenfolgensuche (Lokalisierung) ausführen.|  
|[helpstring](../windows/helpstring.md)|Gibt eine Zeichenfolge, die verwendet wird, um das Element zu beschreiben, auf dem es angewendet.|  
|[hidden](../windows/hidden.md)|Gibt an, dass das Element vorhanden ist, aber nicht in einem Browser benutzerorientierte angezeigt werden soll.|  
|[idl_module](../windows/idl-module.md)|Gibt einen Einstiegspunkt in eine DLL-Datei an.|  
|[idl_quote](../windows/idl-quote.md)|Können Sie Attribute verwenden, oder IDL erstellt, die nicht in der aktuellen Version von Visual C++ unterstützt werden.|  
|[ID](../windows/id.md)|Gibt eine DISPID für eine Memberfunktion (eine Eigenschaft oder eine Methode in einer Schnittstelle oder Disp-Schnittstelle).|  
|[iid_is](../windows/iid-is.md)|Gibt die IID der COM-Schnittstelle, die einen Schnittstellenzeiger verweist.|  
|[immediatebind](../windows/immediatebind.md)|Gibt an, die Datenbank sofort aller Änderungen an eine Eigenschaft eines Objekts von datengebundenen benachrichtigt wird.|  
|[importlib](../windows/importlib.md)|Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.|  
|[import](../windows/import.md)|Gibt eine andere IDL, ODL oder Header-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL-Datei verweisen möchten.|  
|[include](../windows/include-cpp.md)|Gibt einen oder mehrere Headerdateien, in der generierten IDL-Datei eingeschlossen werden sollen.|  
|[includelib](../windows/includelib-cpp.md)|Bewirkt, dass eine IDL oder .h-Datei, in der generierten IDL-Datei eingeschlossen werden sollen.|  
|[in](../windows/in-cpp.md)|Gibt an, dass ein Parameter von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.|  
|[last_is](../windows/last-is.md)|Gibt den Index des letzten Arrayelements übermittelt werden sollen.|  
|[lcid](../windows/lcid.md)|Sie können einen Gebietsschemabezeichner an eine Funktion übergeben.|  
|[length_is](../windows/length-is.md)|Gibt die Anzahl von Arrayelementen übermittelt werden sollen.|  
|[licensed](../windows/licensed.md)|Gibt an, dass die Co-Klasse, für die er gilt, lizenziert ist, und muss mit instanziiert werden **IClassFactory2**.|  
|[local](../windows/local-cpp.md)|Können Sie die MIDL-Compiler als bei der Verwendung in der Schnittstelle Header einen Header-Generator zu verwenden. Wenn in einer einzelnen Funktion verwendet wird, kennzeichnet eine lokale Prozedur für die keine Stubs generiert werden.|  
|[max_is](../windows/max-is.md)|Legt fest, den maximalen Wert für eine gültige Arrayindex.|  
|[Modul](../windows/module-cpp.md)|Definiert den Bibliotheksblock in der IDL-Datei.|  
|[ms_union](../windows/ms-union.md)|Steuert die Netzwerk-datenausrichtung Darstellung nonencapsulated Unions.|  
|[no_injected_text](../windows/no-injected-text.md)|Verhindert, dass den Compiler Code aufgrund der Verwendung des Attributs injiziert.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaftenbrowser angezeigt werden soll.|  
|[noncreatable](../windows/noncreatable.md)|Definiert ein Objekt, das allein nicht instanziiert werden kann.|  
|[nonextensible](../windows/nonextensible.md)|Gibt an, dass die `IDispatch` Implementierung enthält nur die Eigenschaften und Methoden aufgelistet, die in die schnittstellenbeschreibung und können nicht mit zusätzlichen Elementen zur Laufzeit erweitert werden.|  
|[object](../windows/object-cpp.md)|Identifiziert eine benutzerdefinierte Schnittstelle an. gleichbedeutend mit der benutzerdefinierten Attributs.|  
|[odl](../windows/odl.md)|Identifiziert eine Schnittstelle als Schnittstelle Objekt Description Language (ODL).|  
|[oleautomation](../windows/oleautomation.md)|Gibt an, dass eine Schnittstelle mit der Automatisierung kompatibel ist.|  
|[Dies ist optional](../windows/optional-cpp.md)|Gibt ein optionaler Parameter für eine Memberfunktion an.|  
|[out](../windows/out-cpp.md)|Gibt die Zeigerparameter an, die von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben werden (vom Server an den Client).|  
|[pointer_default](../windows/pointer-default.md)|Gibt das Standardattribut für die Zeiger für alle Zeiger mit Ausnahme der obersten Ebene Zeigern, die angezeigt werden in Parameterlisten an.|  
|[pragma](../windows/pragma.md)|Gibt die angegebene Zeichenfolge, ohne die Anführungszeichen in der generierten IDL-Datei aus.|  
|[progid](../windows/progid.md)|Gibt an, die ProgID für ein COM-Objekt.|  
|[propget](../windows/propget.md)|Gibt eine Eigenschaft Accessor (Get)-Funktion.|  
|[propputref](../windows/propputref.md)|Gibt eine eigenschaftseinstellungsfunktion an, die einen Verweis anstelle eines Werts verwendet.|  
|[propput](../windows/propput.md)|Gibt eine Eigenschaftseinstellungsfunktion an.|  
|[ptr](../windows/ptr.md)|Kennzeichnet einen Zeiger als vollständige Zeiger.|  
|[public](../windows/public-cpp-attributes.md)|Stellt sicher, dass eine Typdefinition in der Typbibliothek aufgenommen werden, auch wenn es nicht von innerhalb der IDL-Datei verwiesen wird.|  
|[range](../windows/range-cpp.md)|Gibt einen Bereich der zulässigen Werte für die Argumente oder Felder, deren Werte zur Laufzeit festgelegt werden.|  
|[readonly](../windows/readonly-cpp.md)|Verhindert die Zuweisung zu einer Variablen.|  
|[ref](../windows/ref-cpp.md)|Identifiziert einen Verweiszeiger an.|  
|[requestedit](../windows/requestedit.md)|Gibt an, dass die Eigenschaft unterstützt die **OnRequestEdit** Benachrichtigung.|  
|[restricted](../windows/restricted.md)|Gibt an, dass es sich bei einer Bibliothek oder einem Mitglied ein Modul, Schnittstelle oder Disp beliebig aufgerufen werden kann.|  
|[retval](../windows/retval.md)|Kennzeichnet den Parameter, der den Rückgabewert des Members empfängt.|  
|[size_is](../windows/size-is.md)|Gibt die Größe des Arbeitsspeichers für Größe Zeiger belegt, Größe von Zeigern auf großen Zeiger und Einzel- oder mehrdimensionale Arrays.|  
|[Datenquelle](../windows/source-cpp.md)|Gibt an, dass ein Mitglied aus einer Klasse, Eigenschaft oder Methode eine Quelle von Ereignissen ist.|  
|[string](../windows/string-cpp.md)|Gibt an, dass das eindimensionale `char`, `wchar_t`, **Byte**, oder das entsprechende Array oder der Zeiger auf ein solches Array als Zeichenfolge behandelt werden muss.|  
|[switch_is](../windows/switch-is.md)|Gibt den Ausdruck oder einen Bezeichner fungiert als die union kombiniert werden sollen, die den union-Member auswählt.|  
|[switch_type](../windows/switch-type.md)|Identifiziert den Typ der Variablen als die union Discriminant verwendet.|  
|[transmit_as](../windows/transmit-as.md)|Weist den Compiler einen übertragenen Typ dargestellten Typen: veränderungsmöglichkeiten für die Client- und serveranwendungen zugeordnet werden soll.|  
|[uidefault](../windows/uidefault.md)|Gibt an, dass die Typmember Informationen das Standardelement für die Anzeige in der Benutzeroberfläche.|  
|[unique](../windows/unique-cpp.md)|Gibt einen eindeutigen Zeiger.|  
|[usesgetlasterror](../windows/usesgetlasterror.md)|Wird dem Aufrufer mitgeteilt, dass wenn ein Fehler aufgetreten ist, wenn diese Funktion aufgerufen wird, klicken Sie dann der Aufrufer aufrufen kann `GetLastError` auf den Fehlercode abzurufen.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.|  
|[v1_enum](../windows/v1-enum.md)|Weist der angegebene enumerierten Typ als eine 32-Bit-Entität, anstatt die 16-Bit-Standardeinstellung übertragen werden.|  
|[vararg](../windows/vararg.md)|Gibt an, dass die Funktion eine Variable Anzahl von Argumenten akzeptieren.|  
|[vi_progid](../windows/vi-progid.md)|Gibt eine versionsunabhängige Form der ProgID an.|  
|[wire_marshal](../windows/wire-marshal.md)|Gibt einen Datentyp, der für die Übertragung anstelle eines Typs programmspezifische Daten verwendet wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Attribute nach Gruppen](../windows/attributes-by-group.md)   
 [Einschränkungen für Attribute](http://msdn.microsoft.com/en-us/6e6c4329-f667-4869-b991-cbe9cb7a8f61)