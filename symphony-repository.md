````js 
class MealRepository extends EntityRepository
{
    /**
     * Search meal by date
     *
     * @param  integer $userId
     * @param  Date $from (format "2012-05-20")
     * @param  Date $to (format "2013-05-20")
     * @return array<Meal> Meal subset
     */
    public function findByUserAndDates($userId, $from, $to)
    {
        $qb = $this->createQueryBuilder('i')
            ->where('i.mealUser = :user_id')
            ->andWhere("i.mealDate >= :from")
            ->andWhere("i.mealDate <= :to")
            ->orderBy("i.mealDate")
            ->setParameter('user_id', $userId)
            ->setParameter('from', $from)
            ->setParameter('to', $to);

        return $qb->getQuery()->getResult();
    }
````