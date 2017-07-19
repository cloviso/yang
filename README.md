# yang
yang is a Sentimental girl
** this is my first blog **
`public FirmDtlQueryRes process(FirmDtlQueryReq firmDtlQueryReq) {
		List<FirmDtlQueryModel> list = null;
		//if (StringUtils.isNotBlank(firmDtlQueryReq.getFirmName())) {
			list = firmDtlQueryMapper.getFirmList(firmDtlQueryReq);
		//}
		// 构造服务返回的数据
				FirmDtlQueryRes res = new FirmDtlQueryRes();
				List<FirmDtlQueryDtl> firmList = new ArrayList<FirmDtlQueryDtl>();
				if (null != list) {
					for (FirmDtlQueryModel item : list) {
						FirmDtlQueryDtl dtl = new FirmDtlQueryDtl();
						BeanUtils.copyProperties(item, dtl);
						
						firmList.add(dtl);
					}
				}
				
				res.setFirmList(firmList);
				
				return res;	
	}
`
