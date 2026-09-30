# Ejercicio — Base de Datos de Gestión de Citas Médicas y Recetas

Proyecto enfocado en la modelación Entidad-Relación (DER / MER) e implementación de base de datos relacional para un sistema de gestión clínica, administrando pacientes, médicos, turnos de atención, catálogo de medicamentos y detalle de recetas médicas emitidas.

---

## Descripción

El sistema modela una estructura de datos relacional para la administración integral de centros médicos o clínicas. Permite registrar los datos de los pacientes y los profesionales de la salud, coordinar y hacer seguimiento del estado de las citas/turnos médicos asignados, gestionar el catálogo de medicamentos de la institución y prescribir recetas detalladas vinculadas tanto al turno correspondiente como a los medicamentos indicados.

---

## Funcionalidades e Implementación

### Entidades y Atributos

* Paciente:


* id_Paciente: Clave primaria identificadora del paciente.


* Nombre: Nombre(s) del paciente.


* Apellido: Apellido(s) del paciente.


* DNI: Documento nacional de identidad.


* Fecha de Nacimiento: Fecha de nacimiento del paciente.


* Domicilio: Dirección o residencia del paciente.


* Obra social: Cobertura médica o seguro de salud del paciente.




* Medicos:


* id_Medico: Clave primaria identificadora del médico.


* Nombre: Nombre completo o nombre de registro del profesional.


* Especialidad-Principal: Área médica o especialidad primaria.


* Especialidad-Secundaria: Segunda especialidad u orientación profesional.


* Teléfono: Número telefónico de contacto.




* Turnos:


* id_Turnos: Clave primaria identificadora de la cita o turno.


* fecha: Fecha programada para la consulta.


* hora: Horario estipulado para la atención.


* estado: Estado de la cita (ej. programado, atendido, cancelado).


* Diagnostico u observación: Comentarios médicos, diagnóstico o notas clínicas de la consulta.




* Medicamentos:


* id_Medicamentos: Clave primaria identificadora del fármaco.


* Código alfanumérico: Código único identificador de inventario o catálogo del medicamento.


* Nombre comercial: Marca o nombre de fantasía del medicamento.


* Monodroga: Principio activo o droga farmacológica.


* Laboratorio Fabricante: Empresa o laboratorio farmacéutico que lo produce.




* Detalle-Recetas:


* id_Turnos: Clave foránea que asocia la indicación médica al turno de origen.


* id_Medicamentos: Clave foránea que referencia el medicamento prescripto.


* Dosis: Posología e indicaciones de administración recetadas.





---

## Relaciones del Modelo

1. Paciente ↔ Turnos (Relación 1:N):


* Un paciente puede agendar y tener múltiples turnos asignados a lo largo del tiempo, pero cada turno pertenece a un único paciente.




2. Medicos ↔ Turnos (Relación 1:N):


* Un médico atiende múltiples turnos en su agenda, mientras que cada turno es conducido por un profesional médico específico.




3. Turnos ↔ Detalle-Recetas (Relación 1:N):


* En una sola consulta (turno) el profesional puede prescribir múltiples ítems o renglones de medicamentos en la receta.




4. Medicamentos ↔ Detalle-Recetas (Relación N:1):


* Un mismo medicamento de catálogo puede aparecer registrado en múltiples detalles de recetas emitidas.
