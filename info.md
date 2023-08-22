## npm init -y // Подтянуть все данные о проекте, в package.json. 

## sequelize (настройка вместо rat: true) 
async function findAllGroups(studentId) {
  const userGroups = await Group.findAll({
    attributes: ['name', 'id'],
    include: {
      model: Student,
      attributes: ['name', 'id'],
      through: {
        attributes: [],
      },
    },
  });
  console.dir(JSON.parse(JSON.stringify(userGroups)), { depth: null });
}
