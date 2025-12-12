# Reporte de conversaciones con Uxi

Dashboard de análisis en tiempo real para el agente virtual Uxi del portal UXDigital.

## Descripción

Este dashboard permite visualizar y analizar las conversaciones del chatbot Uxi, incluyendo métricas de uso, calificaciones de usuarios y tendencias temporales.

## Características

- 📊 **Métricas en tiempo real**: Total de conversaciones, sesiones únicas, rating promedio y calificaciones
- 📈 **Gráficos interactivos**: Conversaciones por día, por hora, distribución de ratings y evolución temporal
- 📋 **Tabla de conversaciones**: Detalle de mensajes con paginación
- 📥 **Exportar CSV**: Descarga de datos para análisis externo
- 📱 **Diseño responsivo**: Compatible con móviles y tablets

## Configuración

### Requisitos

- Proyecto en Supabase con la tabla `agente_uxi_portal`
- Política RLS habilitada para lectura pública

### Estructura de la tabla

```sql
create table public.agente_uxi_portal (
  id serial primary key,
  session_id varchar(255) not null,
  message jsonb not null,
  created_at timestamp with time zone default now(),
  user_email varchar(255),
  rating integer check (rating >= 1 and rating <= 5),
  rating_comment text
);
```

### Uso

1. Abrir `index.html` en un navegador
2. Ingresar la URL de Supabase: `https://[tu-proyecto].supabase.co`
3. Ingresar la clave anon pública de Supabase
4. Hacer clic en "Conectar y Cargar Datos"

## Filtros disponibles

- **Período**: Todos, Hoy, Última semana, Último mes
- **Rango de fechas**: Selección personalizada con fecha inicio y fin

## Archivos

```
├── index.html    # Dashboard principal
└── README.md     # Este archivo
```

## Tecnologías

- HTML5 / CSS3
- JavaScript (Vanilla)
- Chart.js (gráficos)
- Supabase REST API

## Contacto

**UXDigital** - Tecnología que inspira  
📧 contacto@uxdigital.cl  
📞 (+569) 5046 0657 | (+569) 4271 5347  
🌐 https://uxdigital.cl
