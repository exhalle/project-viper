# Проект автоматизированого CI CD, используя Jenkins 

Как происходит 
- Берется проект из GitHub
- Build by maven
- Публикуется artifact to git 
- *в процессе 
  - Далее берется артифакт копируется в dockerfile -> поднимается docker-compose  
