---
title: "texture_view-Klasse"
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
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# texture_view-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt einer Textur Lese\- und Schreibzugriff zur Verfügung.  `texture_view` kann nur verwendet werden, um Texturen zu lesen, deren Werttyp `int`, `unsigned int` oder `float` mit 32\-Bit\-Standard ist.  Verwenden Sie zum Lesen anderer Texturformate `texture_view<const _Value_type, _Rank>`.  
  
## Syntax  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view : public details::_Texture_base<_Value_type, _Rank>;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view<const _Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
```  
  
#### Parameter  
 `_Value_type`  
 Der Typ der Elemente im Texturaggregat.  
  
 `_Rank`  
 Der Rang des `texture_view`\-Objekts.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`value_type`|Der Typ der Elemente in den Texturaggregaten.|  
|`coordinates_type`|Der Koordinatentyp, mit dem ein Texel im `texture_view`\-Objekt angegeben wird, d. h. ein `short_vector`\-Objekt, das den gleichen Rang wie die zugeordnete Textur mit dem Werttyp `float` hat.|  
|`gather_return_type`|Der Rückgabetyp, der für Erfassungsvorgänge verwendet wird, d. h. ein `short_vector`\-Objekt mit Rang 4, das die vier homogenen Farbkomponenten enthält, die von den vier geprüften Texelwerten erfasst wurden.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture\_view::texture\_view\-Konstruktor](../Topic/texture_view::texture_view%20Constructor.md)|Überladen.  Erstellt eine `texture_view`\-Instanz.|  
|[texture\_view::~texture\_view\-Destruktor](../Topic/texture_view::~texture_view%20Destructor.md)|Zerstört die `texture_view`\-Instanz.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture\_view::gather\_alpha\-Methode](../Topic/texture_view::gather_alpha%20Method.md)|Überladen.  Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die blauen \(w\)\-Komponenten der vier geprüften Texel zurück.|  
|[texture\_view::gather\_blue\-Methode](../Topic/texture_view::gather_blue%20Method.md)|Überladen.  Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die blauen \(z\)\-Komponenten der vier geprüften Texel zurück.|  
|[texture\_view::gather\_green\-Methode](../Topic/texture_view::gather_green%20Method.md)|Überladen.  Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die grünen \(y\)\-Komponenten der vier geprüften Texel zurück.|  
|[texture\_view::gather\_red\-Methode](../Topic/texture_view::gather_red%20Method.md)|Überladen.  Prüft die Textur an den angegebenen Koordinaten mithilfe der angegebenen Samplingkonfiguration und gibt die roten \(x\)\-Komponenten der vier geprüften Texel zurück.|  
|[texture\_view::get\-Methode](../Topic/texture_view::get%20Method.md)|Überladen.  Ruft den Elementwert durch Index ab.|  
|[texture\_view::sample\-Methode](../Topic/texture_view::sample%20Method.md)|Überladen.  Prüft die Textur an den festgelegten Koordinaten und den Detailgrad mithilfe der angegebenen Samplingkonfiguration.|  
|[texture\_view::set\-Methode](../Topic/texture_view::set%20Method.md)|Legt den Wert eines Elements mithilfe des Index fest.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture\_view::operator\(\)\-Operator](../Topic/texture_view::operator\(\)%20Operator.md)|Überladen.  Ruft den Elementwert durch Index ab.|  
|[texture\_view::operatorOperator](../Topic/texture_view::operatorOperator.md)|Überladen.  Ruft den Elementwert durch Index ab.|  
|[texture\_view::operator\= Operator\/\/\/](../Topic/texture_view::operator=%20Operator.md)|Überladen.  Zuweisungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture\_view::value\_type\-Datenmember](../Topic/texture_view::value_type%20Data%20Member.md)|Der Werttyp der Elemente des `texture_view`\-Objekts.|  
  
## Vererbungshierarchie  
 `_Texture_base`  
  
 `texture_view`  
  
## Anforderungen  
 **Header:** amp\_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
## Siehe auch  
 [Concurrency::graphics\-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)