

# **Astro AI Medic**

**Version:** 1.0.0 | **Author:** Opie Winters

**Description:**
Call an AI-controlled medic when no EMS are on duty. The medic drives an ambulance, revives you, and charges a fee automatically.

---

## **Requirements**

* QB-Core 
* qb-management (optional, for society money)

---

## **Installation**

1. Place `astro-aimedic` in your resources folder.
2. Add to `server.cfg`:

```cfg
ensure qb-core
ensure astro-aimedic
```

---

## **Config**

```lua
Config.EMSJob = "ambulance"
Config.Doctor = 0           -- Max EMS online to allow AI
Config.Fee = 500            -- Cost to call AI medic
Config.ReviveTime = 15000   -- CPR animation duration
Config.DoctorPed = "s_m_m_doctor_01"
Config.AmbulanceModel = "ambulance"
```

---

## **Command**

* `/medic` – Call AI medic (only while dead or in last stand)

---

## **How it Works**

1. Checks if EMS online and if player can pay.
2. Spawns ambulance & doctor ped near player.
3. Doctor drives, exits, does CPR, revives player.
4. Player is charged the configured fee.

---

## **Server Event**

* `astro-aimedic:server:DoRevive` – 

---

## **Notes**
* Only works when dead / in last stand.
* Cleans up ambulance and doctor after revive.
* Customize revive time, fee, and models in `config.lua`.

