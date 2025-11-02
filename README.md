# EcoAlerta - Inicio rápido

## Instalar dependencias (obligatorio)
```bash
# Backend
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Frontend
cd ../frontend
npm install
```

## Requisitos
- Python 3.11+
- Node.js 18+ y npm
- macOS/Linux/Windows

## Primera instalación
```bash
# Backend
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py load_initial_data  # categorías + usuario inspector

# Frontend
cd ../frontend
npm install
```

## Ejecutar ambos servicios (recomendado)
```bash
# Desde la raíz del proyecto
./start.sh
# Para detener
./stop.sh
```
- Backend: http://localhost:8000
- Frontend: http://localhost:5173
- Logs: `logs/backend.log`, `logs/frontend.log`

## Ejecutar por separado (opcional)
```bash
# Backend
cd backend
source venv/bin/activate
python manage.py runserver

# Frontend
cd frontend
npm run dev
```

## Credenciales de prueba
- Usuario: `inspector`
- Password: `1234`

## Endpoints principales
- Autenticación: `POST /api/auth/login/`
- Reportes: `GET/POST /api/reportes/`
- Categorías: `GET /api/categorias/`
- Estadísticas: `GET /api/reportes/estadisticas/`

## Solución de problemas
- El puerto 5173 ocupado: Vite arrancará en otro puerto (p. ej. 5174).
- 404 en `/`: es normal. Usa `/api/` o el frontend.
- Si falta `venv`: vuelve a crear y reinstalar dependencias del backend.
