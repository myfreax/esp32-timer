# ESP32 Timer Component
General Software Timer

## Usage
```
git submodule add git@github.com:myfreax/esp32-timer.git components/timer
```
```c
#include "timer.h"

esp_timer_handle_t handle;

void callback(void* arg) {
  esp_timer_handle_t* timer = arg;
  ESP_ERROR_CHECK(esp_timer_delete(*timer));
}

ESP_ERROR_CHECK(
    set_timeout("once", callback, &handle, &handle, time_us));

ESP_ERROR_CHECK(
set_interval("repeat_times", callback, &handle, &handle, time_us));
```