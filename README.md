# ols-router
BC Route Planner NG is a three year project of the Province of British Columbia to develop a state-of-the art route planner. The BC Route Planner NG is a vital component of the free and open DataBC Location Services Platform.

In year 1 (2018-19), we will investigate the feasibility of supporting multiple complex routing constraints including support time-dependent routing including historic traffic congestion, road incidents and closures, road construction, and ferry schedules. The first release will include those components for which there is insufficient or no real data so that developers can start integrating the route planner into their new applications as soon as possible. Tackling data issues is beyond the scope of this project and their resolution may be many months away. The performance goal of the first release is under two seconds for a single, two-point, oversized truck route.

In year 2 (2019-2020), support for truck routing, a road watcher, and new data sources will be added. Truck routing takes vehicle dimensions and road restrictions into account.

In Year 3 (2020-2021), we will focus on incorporating user-requested enhancements, making routes more realistic, and improving performance.

[Current milestones for this year](https://github.com/bcgov/ols-router/milestones)

[Draft year 1 Route Planner release notes](https://github.com/bcgov/ols-router/issues/75)

[Draft Integrated Transportation Network Data Model Gaps](https://github.com/bcgov/ols-router/blob/master/ITN-Data-Mode-Gaps.md)

## Draft System Architecture
The BC Route Planner NG is a web service (aka API) running behind an API Gateway which provides security, metering, and load balancing. Multiple route planner nodes will be deployed across multiple data centres so that service will never be interrupted during rollout of a new release or during a data centre failure.

After a cold restart, the Road Watcher will read in the static road network into an in-memory datastore then update it from real-time sources on a periodic schedule (e.g., every five minutes).

![](https://github.com/bcgov/ols-router/blob/master/BC%20Route%20Planner%20NG%20Architecture.png)
